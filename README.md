# SGAE Environment
- Contenedor base de Ubuntu (ubuntu:14.04)
- Contenedor propio de Flume (1.7.0 con fuentes propios)
- Contenedor propio de Hadoop (2.7.5 con fuentes propios)
- Contenedor propio de Sqoop (1.4.7 con fuentes propios)
- Contenedor oficial de Mysql (5.7 oficial)
- Contenedor oficial de Mysql-server (5.7 oficial)
- Contenedor oficial de Oracle (11 oficial)
- Contenedor propio de Airflow (1.9)
- Contenedor oficial de Kibana
- Contenedor oficial de ElasticSearch (6.2.3)
- Contenedor oficial de Spark (2.3.0)

- El docker-compose.yml arrancará el entorno estrictamente necesario

## Requisites:
- Docker must be installed in the host. 
In ubuntu, it can be installed by following [the official tutorial in docker.com](https://docs.docker.com/install/linux/docker-ce/ubuntu/#set-up-the-repository), please follow the official guide.

Other software used to monitorized and control docker might be very useful such as [Dockstation](https://dockstation.io/) or the docker plugin of your favorite IDE.
In the case of [Intellij](https://www.jetbrains.com/idea/download/#section=linux), it can be installed by looking for docker in the [plugin manager](https://plugins.jetbrains.com/plugin/7724-docker-integration) 

## Preparing the environment:
All images are built and uploaded to [our private gitlab registry](https://gitlab.com/StrategyBD/SGAE/SGAE_PoC/container_registry).
BEFORE executing other commands, you must login on the private registry by following the [previous link](https://gitlab.com/StrategyBD/SGAE/SGAE_PoC/container_registry).

The download will be triggered with the 'docker-compose' command or the `./handle_container.sh` script and it takes around 20 minutes depending on your internet connection.
Follow the next section: **Launching the environment** 

Alternatively, there is another way to prepare the environment which is building the images. This method is **not recommended** as it will take a massive amount of time and resources.
To do so, execute the following script:
- `./build_images.sh`, script that builds the docker images (~60 min.).


## Launches the environment

```sh
./handle_container.sh start
```

## Stops the environment del entorno
```sh
./handle_container.sh stop
```

## Stops active containers and remove them
```sh
./handle_container.sh clean
```

## Checks containers state
```
docker ps
```

## Checks docker logs
```
docker logs [container-name] 
```
