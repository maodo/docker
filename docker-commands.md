## Commands

## Create docker network
docker network create mongo-network

## Start mongo-db
docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo_network mongo
## Start mongo-express
docker run -d \                                                             
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=mongoadmin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
--net mongo_network  \
--name mongo-express \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
mongo-express