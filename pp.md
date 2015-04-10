## Structure
* Node.js web server-client
* Internal batch worker for
  * collecting active users
  * collecting message
  * matching users-message
* Node.js backend admin to
  * monitor messaging
  * manage users
  * manage tags (approval?)
* Internal batch worker to
  * send email on notification
* API server for future usage

## Web server-client
* /home
* /profile
* /message >> message landing
* /message/:messageId >> read message
* /tags/:tagname >> category(tag) landing
* /:username (/:userId)
 