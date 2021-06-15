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