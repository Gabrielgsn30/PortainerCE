# PortainerCE
Instalando o Portainer localmente utilizando Docker

O Portainer é uma ótima ferramenta para ajudar na administração de seus containers, sejam eles locais, ou rodando em modo "swarm". Muito fácil gerenciar os container por causa do modo visual.
Existem também templates caso queira criar alguns tipoos de containers e ainda é possível conectar no sheel de cada container diretamente pela interface, do Portainer.
Bom vimos que o Portainer é uma ótima ferramenta para gerenciamento de containers e ter um modo visual facilita bastante.
mas como é feita a instalação?!

Iremos abortar isso passo a passo.
Primeiro deve criar um volume para o Portainer

```
docker volume create portainer_data
```

Apoś isso subir o container com o comando abaixo, nota-se que o Portainer utiliza duas portas a 8000 e a 9000 também utiliza o docker.sock para ficar 'escutando' os containers volumes redes e tudo que se cria no docker.
```
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```

Basicamente seria isso a instação, após a execução na primeira vez será solicitado criar senha, e após isso terá acesso ao painel.
