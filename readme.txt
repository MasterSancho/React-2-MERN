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