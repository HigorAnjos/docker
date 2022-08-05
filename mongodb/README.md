# hello-mongodb

## Connect

MongoDB Compasss **ou** MongoDB for VS Code
```
mongodb://root:example@localhost:27017/
```

# Docker

Subir o container

```bash
docker-compose up -d
```

<!-- Entrando no container
```docker exec -it <nome-do-contêiner-ou-id> mongo```

```bash
docker exec -it mongodb mongo
``` -->


No primeiro passo, copiamos o arquivo que será importado para dentro do nosso contêiner.

```docker cp nome-do-arquivo.json <nome-do-contêiner-ou-id>:/tmp/nome-do-arquivo.json.json ```
``` bash
docker cp superheroes.json mongodb:/tmp/superheroes.json
```


No segundo passo, realizamos a importação do arquivo **JSON** para o MongoDB.

```docker exec <nome-do-contêiner-ou-id> mongoimport -d <nome-do-banco> -c <nome-da-coleção> --file /tmp/nome-do-arquivo.json```

```bash
docker exec mongodb mongoimport -d class -c superheroes --file /tmp/superheroes.json
```

[seeding-mongodb-docker-compose](https://shantanoo-desai.github.io/posts/technology/seeding-mongodb-docker-compose/)