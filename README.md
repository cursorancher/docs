# Docs

## Checklist

* Máquina com Ubuntu, RedHat ou RancherOS
* Portas 80 e 443 liberadas
* Docker

## Instalando o Docker

Para instalar o Docker, na versão 18.03, basta executar o comando abaixo em sua instância:

```bash
curl https://releases.rancher.com/install-docker/18.03.sh | sh
```

## Instalando o Rancher 2.x

A versão 2 tornou o processo mais fácil de ser executado, e vem por padrão com um certificado auto-assinado incluido. Sendo assim. é necessária a liberação da porta **80** e da porta **443**. Para iniciar o rancher 2, execute o seguinte comando:

```bash
sudo docker run -dit --restart=unless-stopped --name rancher -v /data/rancher:/var/lib/mysql -p 80:80 -p 443:443 rancher/rancher
```

E para quem gosta/utiliza o docker-compose, segue abaixo o padrão:

```yaml
version: '2'
services: 
  rancher:
    image: rancher/rancher
    restart: unless-stopped
    volumes:
        - /data/rancher:/var/lib/mysql
    ports:
      - 80:80
      - 443:443
```
