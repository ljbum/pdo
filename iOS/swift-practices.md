# Swift Practice
## OAuth2 Client
* http://oauth.net/documentation/

### OAuth2 Simplified
* Client: Third-party application
* Resource Server: API itself
* Resource Owner: User, giving access to their account
* Authorization Server
  * the server issuing access tokens to the client after successfully authenticating the resource owner and obtaining authorization 

#### Authorization
* Redirect URIs
* Client ID
* Client Secret
  * not used in Javascript or Native apps (in some cases)

##### - GrantType: Password
* [grant_type: password] is used to exchange for access_token in third-party apps (custom client)

```
POST https://oauthServer/token
grant_type=password&
uesrname=USERNAME&
password=PASSWORD&
client_id=CLIENT_ID
```

* The client secret is not included under assumption that secret will not be protected

##### - GrantType: Client_credentials
* If applications need a way to get access token outside the context of any specific user, grant_type: client_credentials are provided

```
POST https://oauthServer/token
grant_type=client_credentials&
client_id=CLIENT_ID&
client_secret=CLIENT_SECRET
```

#### Making Authenticated Requests
* with an access_token, you can make requests to the API

```
curl -H "Authorization: Bearer ACCESS_TOKEN" \
https://oauthServer/example/api/path
```

### OAuth2 RFC
* [OAuth2 Framework RFC](http://tools.ietf.org/html/rfc6749)

```
     +--------+                               +---------------+
     |        |--(A)- Authorization Request ->|   Resource    |
     |        |                               |     Owner     |
     |        |<-(B)-- Authorization Grant ---|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(C)-- Authorization Grant -->| Authorization |
     | Client |                               |     Server    |
     |        |<-(D)----- Access Token -------|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(E)----- Access Token ------>|    Resource   |
     |        |                               |     Server    |
     |        |<-(F)--- Protected Resource ---|               |
     +--------+                               +---------------+

                     Figure 1: Abstract Protocol Flow
```



### Token storing: NSUserDefaults vs Keychain

* NSUserDefaults is not secure or encrypted
* [Reference](http://stackoverflow.com/questions/16795506/storing-authentication-tokens-on-ios-nsuserdefaults-vs-keychain)

#### - NSUserDefaults <small>[Reference](http://www.codingexplorer.com/nsuserdefaults-a-swift-introduction/)</small>

* NSData, NSString, NSNumber, NSDate, NSArray, NSDictionary
* <b>do not use synchronize in iOS 8 and later</b>
* NSURL (not being a plist type) needs to be serialized into an NSData before being set