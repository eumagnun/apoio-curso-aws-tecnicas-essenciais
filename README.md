# Material de apoio ao curso AWS | Técnicas Essenciais 🙂

## Arquivos disponibilizados 📚
 
 - HeidiSQL_11.0_64_Portable.zip -> Client portable para acesso MYSQL
 - index.html -> Página HTML simples para teste do S3 como host
 - maiores_arrecadacoes_cinema_2020.csv -> Massa de dados para teste de queries via S3
 - rds.png -> Amostra de setup para criação de instância RDS - MySQL
 - mineradora-ativos-frontend.zip -> frontend da aplicação final (em \build\static\js\main.14649292.chunk.js e \build\static\js\main.14649292.chunk.js.map trocar o IP e porta pelo em uso de fato)
 
 
## Exercicio Final 👨‍🎓🤘

## VPC:

Criar nova VPC (public e private) vi wizard
Após a criação da VPC teremos duas subnets. Criar uma terceira subnet, do tipo privada em uma zona disponibilidade diferente da primeira.

Criar Security Group "sg_aplicacao" com regras abaixo:
origem 0.0.0.0/0	 porta: 22
origem 0.0.0.0/0	 porta: 8080 - 8089

Criar Security Group "sg_db" com regras abaixo:
origem sg_aplicacao	 porta: 80
origem sg_aplicacao	 porta: 22
origem sg_aplicacao	 porta: 3306


## RDS: 
Criar subnet group com as duas subnets privadas
Criar rds com subnet-group definido e vpc definida

anotar url, user and pass

## EC2:
criar maquina na subnet publica

Acessar máquina e instalar aplicação seguindo os passos abaixo:

- apt-get update
- apt-get upgrade

- sudo apt install default-jdk
- java -version

- sudo apt-get -y install maven
- mvn -version

- git clone https://github.com/eumagnun/mineradora-ativos.git

- cd mineradora-ativos/mineradora-ativos-service/

- mvn package

- java -jar target/service.jar [--server.port=8080]


Acessar url:
http://IP_PUBLICO:8080/swagger-ui.html#/


## S3

Criar bucket para hospedagem de site

aplicar politica de liberação de acesso:

```
{
  "Version":"2012-10-17",
  "Statement":[
    {
      "Sid":"PublicRead",
      "Effect":"Allow",
      "Principal": "*",
      "Action":["s3:GetObject","s3:GetObjectVersion"],
      "Resource":["arn:aws:s3:::XXXXXX/*"]
    }
  ]
}
```

Implantar frontend da aplicação conform passos abaixo:

- 
- 
- 

