# ELK -  ElasticSearch, Logstash, and Kibana

### Ambiente en produccion
ElasticSearch se encuentra con su base de datos en estado persistente para produccion, se utliza EFS en AWS
el disco es montado en todos los servidores del cluster y dentro del disco se dejara al proyecto, esto con el fin de que todos nodos puedan escribir en el disco de datos persistentes de ELK.


#En produccion con docker swarm

Una vez en el directorio elk

Ajustar memoria virutal

sysctl -w vm.max_map_count=262144

se debe asegurar que los directorios de datos persistentes tengan permiso de escritura

# para arrancarlo en el un solo host
$ docker stack deploy --compose-file docker-compose.yaml elk. 

# swarm mode
$ docker-compose up -d # para correr todo en un solo servidor

para detenerlo

# swarm mode
$ docker stack rm elk. 

# para detenerlo en el un solo host

$ docker-compose down 
 

