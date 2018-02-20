# Activity06 - Annotations
## Jennifer Podracky

### Intro
The below series of commands took place on a Digital Ocean droplet.

### Annotations

Make a directory to create the docker container in.
```
   82  mkdir activity06-jmercado14
  ...

   86  cd activity06-jmercado14/
```

Clone the git repository containing the docker-compose.yml into the file.
```
   90  git clone https://github.com/jmercado14/w205-activity06-temp
```

Copy the contents of https://goo.gl/f5bRm4 into the assessment-attempts-20180128-nested.json file.
```
  116  curl -L -o assessment-attempts-20180128-nested.json https://goo.gl/f5bRm4
```

Spin up a docker cluster using the configuration specified in the docker-compose.yml file.
```
  157  docker-compose up -d
  158  docker-compose ps
```

Install kafkacat onto the container.
```
  163  sudo apt-get install kafkacat
```

Execute a command that does the following on the mids bash shell:
* look at the assessment-attempts-20180128-nested.json file
* pull out array values
* produce a topic called 'foo' on the kafka:29092 broker
* Print 'Produced 100 messages.' to the shell
```
  171  docker-compose exec mids bash -c "cat /w205/assessment-attempts-20180128-nested.json | jq '.[]' -c | kafkacat -P -b kafka:29092 -t foo && echo 'Produced 100 messages.'"
```

```
  172  history > jmercado14-history.txt
```
