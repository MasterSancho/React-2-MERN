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