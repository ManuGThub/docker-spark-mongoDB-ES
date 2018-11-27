# Docker Spark-HDFS-ElasticSearch-MongoDB

To run the environment, first of all you have to build the HDFS image locally with the following command from the docker-spark-mongoDB-ES folder:

```./build_images.sh start```

once the process is finished:

```docker-compose up -d```

and the environment should be up without any errors

then you could open the Scala Proyect called: proyectoInserciones and run it from the Main class.

It will do the following data flow:

local ---> HDFS<br />
HDFS ---> ElasticSearch<br />
ElasticSearch ---> MongoDB<br />

and compare the result DataFrame with the original one, displaying the result

OR

just compile and build the proyect 

once the proyect is built, copy the .jar into the spark master container

```docker cp [path_yo_jar]/proyectoInserciones.jar insert_spark-master:/proyectoInserciones.jar```

then run the following command to get into the Spark master docker container

```docker exec -it master /bin/bash```

and run the following command to submit the job

```spark-submit \
  --class Main \
  --master spark://master:7077 \
  /proyectoInserciones.jar [parameters]
```
