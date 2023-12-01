## This repo is for the goalert docker compose setup with external postgressdb 


## befor running this pleas use a kevault for reciving passwords or run this under userprivs that only you can access 

```bash 
docker-compose up -d
```
## After the containers are both up and running u need to add a user to the goalert container and you can do so by using the following steps:

1) get a shell into the container 
```bash 
docker exec -it $(docker ps | grep 'goalert/goalert' |awk '{print $1}') sh
```
2) add the user form within the container 
```bash
goalert add-user --db-url $GOALERT_DB_URL --admin --user admin --email <<email.addr>>
```
3) exit and go on the web interface 
