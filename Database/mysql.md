# MySQL

## Connection Pooling
* By using the object which can manage the connection, it brings the connection to single thread and return when the work is done.
* The object, connectionPool, check the status and manage the numbers of connection.
* Pros:
  * Save time on creating connection. (reuseability)
  * Almost same as create new connection
  * Manage system resource effectively

### Reference
* [KOR::Node.js-MySQL](http://bcho.tistory.com/892)
* [Official Docs: Chapter 7 Connection Pooling with Connector/J](http://dev.mysql.com/doc/connector-j/en/connector-j-usagenotes-j2ee-concepts-connection-pooling.html)