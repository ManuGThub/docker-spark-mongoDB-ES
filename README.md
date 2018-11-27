# Docker Spark-HDFS-ElasticSearch-MongoDB

To run the environment, first of all you have to build the HDFS image locally with the following command from the docker-spark-mongoDB-ES folder:

´´´./build_images.sh start´´´

once the process is finished:

´´´docker-compose up -d´´´

and the environment should be up without any errors

then you could open the Scala Proyect called: proyectoInserciones and run it from the Main class.

It will do the following data flow:

local ---> HDFS
HDFS ---> ElasticSearch
ElasticSearch ---> MongoDB

and compare the result DataFrame with the original one, displaying the result
