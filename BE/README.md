##**✈Grocery-APP Dockerfile✈**

### ✅ Prerequisites
Your backend server and frontend server need to be in the same server or instance, or you can also use different servers too, but you have to configure the same base Docker image, like if you have used Ubuntu for the backend EC2, then for the frontend also use the same Ubuntu.

I have used Docker Ubuntu image (to download docker image you can refer to the link https://docs.docker.com/engine/install/ubuntu/)

### run following command on mongodb view your data

mongosh
use grocerydb
db.groceries.find()


### note :- if you want to create mongodb server seprately ensure you enlist the mongodbserver ip in server.js files mentioned string if fe , be , db is in same server then do not change anything in the code.

// Connect to MongoDB
mongoose.connect("mongodb://IPOfMongoDbServer:27017/grocerydb"

