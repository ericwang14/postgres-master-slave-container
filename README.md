# postgres-master-slave-container
example of set up Postgres database master slave replication using docker


there's 2 way to run this example.

1. docker compose, docker-compose up &
	

2. docker stack with docker swarm enabled, docker stack deploy -c docker-stack.yml my-replication.


by default the container not expose any port number, if you can expore the master slave replication you can 
1. get in the docker container by following steps
	a. docker exec -ti {container id} /bin/sh, container id is your master container id
	b. run psql -U hamed
	c. "\d" means describle the tables, list all the tables, by default no table, you can create your own table, and if will be replicated to  the slaves.
	d. "\q" to quit the psql.
	e. same step as #a use slave container id, and same step as #b check the tables and data.

2. or you can modify the docker-compose.yml to add ports config, like 
    ports:
      - 5432:5432

    be careful with the 2 containers, they can't map to the same port on the host machine, use different one.
    the ports will be opened and then you can use the ip address and ports to connect the database.

 
