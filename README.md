# Gelato, management app

With Gelato, every icecream maker can manage his cakes production with ease.

You can set a cake with:
- flavours
- number of persons
- a shape
- miscellanous stuff
- a client (name, address, phone)
- a delivery date
- a state (Not started, WIP, done, gone)

You can also manage your clients and send them emails.

### Installation

Clone or download the repository

In the .env file of the main folder:
  - Create a Mongodb database cluster at https://www.mongodb.com/
  - Retrieve your connection string from the "connect" button in your clusters home page
  - After clicking connect find "Connect your application"
  - Copy your connection string
  - Replace the text after "DATABASE:" with your Mongodb database connection string.
  - Change the JWT_SECRET *this is used to encode the JSON Web Token

### .env

  - PORT = The port number of your server
  - DATABASE = Your Mongo database string
  - JWT_SECRET = The long string you use to encode your Json Web Token 
  - JWT_EXPIRES = Length of time the JWT is good for ex: 14d = 14 days
  - JWT_EXPIRATION_NUM = Length of time the JWT is good for in milliseconds ex: 14*24*60*60*1000 = 14 days
  - NODE_ENV = 'dev' for development || 'production' for production
 
### authController.secure

Purpose: Secure routes from users who are not logged in. 

Usage: Place on or before routes that are only available to logged in users

App Example: In use before of the secret route in routes -> authRoutes

### authController.clearanceLevel

Purpose: Secure routes from users who do not hold the proper 'Clearance' credentials in their user schema. 

Usage: Define the clearance levels needed to retrieve the content in the function arguments. ex authController.clearanceLevel('level 1', 'level 2')

App Example: In use before of the secret route in routes -> authRoutes

### authController.blacklist

Purpose: Create a list of keywords that are rejected from req.body

Usage: Remove keywords from req.body. ex: authController.blacklist('clearanceLevel', 'version')

App Example: In use before of the secret route in routes -> authRoutes


### Tech

AuthReactMongo uses the following tech stack:

  - Mongodb
  - Express
  - React
  - Nodejs
  - Mongoose
  - Redux

License
----

MIT
