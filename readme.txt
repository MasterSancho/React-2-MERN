=> { npx create-react-app frontend }
&&
{ cd frontend } && { npm start }


=> Take GIT to root folder
{ rm -rf .git }
&&
move ( .gitignore ) to root folder
&&
( .gitignore ) PUT ->
{
 # dependencies
node_modules
node_modules/
}
&&
{
 # misc
.DS_Store
.env
}


=> I Bootstrap with Bootswatch
Bring Theme file from Bootswatch to src folder
&&
{
 import ReactDOM from 'react-dom';
 import './bootstrap.min.css'
}
&&
in terminal
{ cd frontend } -> { npm i react-bootstrap }


=> bring font-awesome ( Icons )
go to cdnjs.com && copy link font-awesome


=> Router
in frontend
{ npm i react-router-dom react-router-bootstrap }
__________________________________________________

=> BackEnd
{ npm init }
&& -> Express
{ npm i express }
&&
Terminal coomand -> { node backend/server }


=> Axios
{ npm i axios }


=> { npm i -D nodemon concurrently }
&& { npm run dev } -> running backend & frontend


=> { npm i dotenv }


=> create .env file ->
{
 NODE_ENV = development
 PORT = 5000
}
_______________________________________________________________

=> Mongo DB
in mongodb.com create new Cluster ->
Database Access { Add New Database User } ->
-> Password Auth ( Name & Password )
&&
Network Access { Add Ip Address }
&&
go to Clusters -> click Collections -> & { Add My Own Data } ->
-> DATABASE NAME { proshop } & COLLECTION NAME { products }
&&
go to Clusters -> click Connect -> { Connect using MongoDB Compass } ->
-> { I have MongoDB Compass } -> copy string ->
-> go to Compass past string ->
{ mongodb+srv://brad1234:<password>@webroker.ebkim.mongodb.net/test }
&& chg name & password ->
{ mongodb+srv://brad1234:brad1234@webroker.ebkim.mongodb.net/proshop }
--------------------------------------------------------------------

=> Mongoose -> { npm i mongoose }

=> Colors -> { npm i colors }
----------------------------------------------------------------------

=> Hash for passwords { npm i bcryptjs }


=> import data to MongoDB { npm run data:import }
* Import Data is replaces everything
&&
=> for destroy data from MongoDB { npm run data:destroy }


=> Instead (try/catch on routes) -> { npm i express-async-handler }
--------------------------------------------------------------

=> PostMan
-> Create new collection
-> Add new folder -> Add request
{ GET /api/products } & { Get all products }
write { http://localhost:5000/api/products }
&&
-> sittings -> Add Environment -> variable { URl }
initial value { http://localhost:5000 }
now link { {{URL}}/api/products }
&&
click Save to save request
-----------------------------------------------------

=> Redux
cd frontend { npm i redux react-redux redux-thunk redux-devtools-extension }


=> Test for error
in ( productRoutes ) file add {
 router.get(
 '/',
 asyncHandler(async (req, res) => {
  const products = await Product.find({});
  res.status(401);
  throw new Error('Not Authorized'); OR { throw new Error('Some error'); }
  res.json(products);
 })
);
}
-------------------------------------------------

=> Users & Auth
in PostMan create new folder ( Users & Auth ) ->
Add request ( POST /api/users/login ) -> { {{URL}}/api/users/login } ->
go to Body -> ( raw ) -> text to ( JSON ) ->
{
 "email": "test@example.com",
 "password": 12345
}
------------------------------------------

=> jwt.io
{ npm i jsonwebtoken }

=> in PostMan
add new request { GET /api/users/profile }
{ {{URL}}/api/users/profile }


=> Take the token &&
in ( profile ) go to Headers
{
 key: Authorization
 value: Bearer TOKEN
}

=> PostMan variable for TOKEN
in Login Tab go to ( Tests ) ->
{ pm.environment.set("TOKEN", pm.response.json().token) } ->
in Profile Tab go to Authorization &&
choose Bearer Token && {{TOKEN}}


=> Postman
( new request ) -> { {{URL}}/api/users } ->

In Users tab go to body click { raw } && { JSON } ->
in Body
{
 "name": "Steve Smith",
 "email": "steve@example.com",
 "password": "123456"
}

-----------------------------------------------

=> Check with Postman User Profile Update ->
new request { PUT /api/users/profile } ->
{ {{URL}}/api/users/profile } ->
Body -> raw -> JSON ->
Authorization -> Bearer Token -> {{TOKEN}}

-----------------------------------------------

=> PostMan
create new folder ( Orders ) -> add new request { GET /api/orders/:id } ->
{ {{URL}}/api/orders/60d20e9a5ecf4b4ac414919e } ->
Authorization ( Bearer Token ) -> ( {{TOKEN}} )
-------------------

=> Go to developer.paypal.com ->
SANDBOX -> Accounts ->
back to My Apps -> proshop -> copy ( Client ID ) ->
In ( .env ) ->
{
 PAYPAL_CLIENT_ID = AUi-PuS1zvig-J6O4xI3n-2_cwmTq0TXY_WlgRL_rzRsTVmFDRqUTgWAHvoWeRE4Gwe4bR5Q3FzpBx-n
 } ->
 paypal sdk script ->
 {
  <script src="https://www.paypal.com/sdk/js?client-id=YOUR_CLIENT_ID"></script>
 }

=> react-paypal-button-v2
{ cd frontend } -> { npm i react-paypal-button-v2 }
--------------------------------------------------------------

=> PostMan ->
add new request on ( Orders ) folder -> { GET /api/orders/myorders } ->
{ {{URL}}/api/orders/myorders } ->
Authorization -> ( Bearer Token )
---------------------------------------------------------------

=> PostMan -> ( GET /api/users ) -> ( Get all users. Admin only ) ->
{ {{URL}}/api/users } ->
Authorization -> ( Bearer Token )
----------------------------------------------------------------

=> PostMan Delete User ->
( DELETE /api/users/:id ) -> ( Delete a user. Admin only ) ->
( {{URL}}/api/users/60cf3d22f762be3cac4193dd ) ->
Authorization -> ( Bearer Token )
-------------------------------------------------------------

=> PostMan Get User by Admin ->
( GET /api/users/:id ) -> ( Get user by ID. Admin only ) ->
( {{URL}}/api/users/60d45939a5303e46d49edc3a ) ->
Authorization -> ( Bearer Token )
-------------------------------------------------------------

=> PostMan Update User by Admin ->
( PUT /api/users/:id ) -> ( Update a user by ID. Admin only ) ->
( {{URL}}/api/users/60d45939a5303e46d49edc3a ) ->
Authorization -> ( Bearer Token ) ->
Body -> { raw } & { JSON } ->
{
 {
    "name": "Alex Maltsev"
 }
}
-------------------------------------------------

=> PostMan Delete Product ->
( DELETE /api/products/:id ) && ( Delete product. Admin only ) ->
Authorization -> ( Bearer Token )
----------------------------------------

=> PostMan Add new Product ->
( POST /api/products ) -> ( Add new sample product ) ->
Authorization -> ( Bearer Token )
-------------------------------------------

=> Update a Product ->
( PUT /api/products/:id ) -> ( Update a product ) ->
Authorization -> ( Bearer Token ) ->
Body -> { raw } & { JSON } ->
{
   {
    "name": "Test Product",
    "description": "Test description",
    "price": 100,
    "category": "Galaxy",
    "image": "/images/sample.jpg",
    "brand": "Solar System",
    "countInStock": 5
 }

}