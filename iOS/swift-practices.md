# Swift Practice
## OAuth2 Client
* [OAuth2 Framework RFC](http://tools.ietf.org/html/rfc6749)
* http://oauth.net/documentation/

### OAuth2 Simplified
* Client: Third-party application
* Resource Server: API itself
* Resource Owner: User, giving access to their account

#### Client specific information
* Redirect URIs
* Client ID
* Client Secret
  * not used in Javascript or Native apps

### Token storing: NSUserDefaults vs Keychain

* NSUserDefaults is not secure or encrypted
* [Reference](http://stackoverflow.com/questions/16795506/storing-authentication-tokens-on-ios-nsuserdefaults-vs-keychain)

#### NSUserDefaults <small>[Reference](http://www.codingexplorer.com/nsuserdefaults-a-swift-introduction/)</small>

* NSData, NSString, NSNumber, NSDate, NSArray, NSDictionary
* <b>do not use synchronize in iOS 8 and later</b>
* NSURL (not being a plist type) needs to be serialized into an NSData before being set