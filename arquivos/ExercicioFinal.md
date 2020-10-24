# Material de apoio ao curso AWS | Técnicas Essenciais 🙂

## Arquivos disponibilizados 📚
 
## VPC:

criar VPC (public e private)
criar subnet privada extra em outra AZ

criar Securty Group "sg_db" com regras abaixo:
origem sg-045d1c6562cbc1a87 (sg_aplicacao)	 porta: 80
origem sg-045d1c6562cbc1a87 (sg_aplicacao)	 porta: 22
origem sg-045d1c6562cbc1a87 (sg_aplicacao)	 porta: 3306

criar Security Group "sg_aplicacao" com regras abaixo:
origem 0.0.0.0/0	 porta: 22
0.0.0.0/0		 porta: 8080 - 8089

## RDS: 
criar subnet group com as duas subnets privadas
criar rds com subnet-group definido e vpc definida

anotar url, user and pass

## EC2:
criar maquina na subnet publica

sudo apt install default-jdk
java -version

sudo apt-get -y install maven
mvn -version

git clone https://github.com/eumagnun/mineradora-ativos.git

cd mineradora-ativos/mineradora-ativos-service/

mvn package

java -jar target/service.jar [--server.port=8080]


Acessar url:
http://3.95.58.192:8080/swagger-ui.html#/


## S3

criar bucket para hospedagem de site

aplicar politica de liberação de acesso:

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
