<div style="text-align:center">
  <img src="https://www.notion.so/image/https%3A%2F%2Fwww.mundodocker.com.br%2Fwp-content%2Fuploads%2F2015%2F06%2Fdocker_facebook_share.png?table=block&id=beb94f94-4d96-46fb-84ff-bce160faa354&spaceId=7043cbd6-4cca-4f7d-bd64-4dbb20f322e0&width=250&userId=71414c58-2576-4515-8b95-6e9474e84114&cache=v2"/>
</div>

# Iniciando com Docker

```docker
// Mostra todos os containers até os que já foram parados
docker ps -a

// -it é a junção de -i interative -t terminal (é o terminal interativo baseado no
// imagem que foi utilizada e no caso bash é o comando que vai rodar dentro do ubuntu
docker run -it ubuntu bash

// -p significa que a porta 8080 da minha maquina vai acessar a porta 80 do container
docker run -p 8080:80 nginx

// -d significa deatached o que não faz o terminal travar quando algum comando 
// normalmente trava ele
docker run -d -p 8080:80 nginx
```

# Trabalhando com imagens



```docker
Dockerfile
FROM ubuntu:latest

// é possivel substituir o parametro exemplo:
// docker run ghisluizgustavo/hello echo "oi"
CMD ["echo", "Hello World"]

// entrypoint vai ser sempre fixo, já o CMD como é parametro
// ele funciona como parametro para o entrypoint
ENTRYPOINT ["echo", "Hello"]
CMD [ "World" ]

```
```docker
docker build -t nome-da-imagem .
```


# Networks

```
bridge  -> containers podem se comunicar facilmente entre si (MAIS COMUM)
host    -> containers podem acessar o próprio host do docker (no caso da máquina local)
overlay -> casos de escabilidade onde containers podem um se comunicar com o outro (DOCKER SWARM)
maclan  -> 
none    -> quando nao tem nenhum tipo de rede container roda de forma isolada
```