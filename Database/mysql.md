# MySQL

## Connection Pooling
* By using the object which can manage the connection, it brings the connection to single thread and return when the work is done.
* The object, connectionPool, check the status and manage the numbers of connection.
* Pros:
  * Save time on creating connection. (reuseability)
  * Almost same as create new connection
  * Manage system resource effectively

```
var mysql = require('mysql');
var thunkify = require('thunkify');
var config = require('./config');

var queryFormat = function queryFormat(query, values) {
    if(Array.isArray(values) || (typeof values)!=='object' ){
        values = values == null ? [] : [].concat(values);

        return query.replace(/\?\??/g, function(match) {
            if (!values.length) {
                return match;
            }

            if (match == "??") {
                return mysql.escapeId(values.shift());
            }
            return mysql.escape(values.shift());
        });
    }else {
        if (!values) return query;
        var result;

        result = query.replace(/\:\:(\w+)/g, function (txt, key) {
            if (values.hasOwnProperty(key)) {
                return values[key];
            }
            return txt;
        }.bind(this));

        result = result.replace(/\:(\w+)/g, function (txt, key) {
            if (values.hasOwnProperty(key)) {
                return this.escape(values[key]);
            }
            return txt;
        }.bind(this));
        return result;
    }
};

mysql._createPool = mysql.createPool;
mysql.createPool =  function(options){
    var connection  = mysql._createPool(options);
    connection._query = thunkify(connection.query);
    connection.query = function *(sql,values){
        return (yield connection._query(sql,values))[0];
    };
    connection.queryOne = function *(sql,values){
        return (yield connection._query(sql,values))[0][0];
    };

    connection.close = thunkify(connection.end);
    return connection;
};

var pool = mysql.createPool({
    host: config.db.hostname,
    user: config.db.user,
    password: config.db.password,
    database: config.db.database,
    port: config.db.port,
    debug:config.db.debug,
    connectionLimit:config.db.connectionLimit,
    timezone: config.db.timezone,
    queryFormat: queryFormat
});

module.exports.pool = pool;
```

### Reference
* [KOR::Node.js-MySQL](http://bcho.tistory.com/892)
* [Official Docs: Chapter 7 Connection Pooling with Connector/J](http://dev.mysql.com/doc/connector-j/en/connector-j-usagenotes-j2ee-concepts-connection-pooling.html)