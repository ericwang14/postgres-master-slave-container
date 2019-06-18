# postgres-master-slave-container
example of set up Postgres database master slave replication using docker


to run this replication example, you will have to setup docker swarm

1. docker swarm init
2. docker stack deploy -c docker-compose.yml my_pg_replication
