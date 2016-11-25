# loja-teste

Estou aprendendo a mexer com Wordpress+Woocommerce, esse repositório vai guardar o código que estou fazendo e o banco de dados, e estou usando Docker para rodar.

## Para criar o container rodar:
    docker run -d --name=lemp \
      -v /path/to/www/:/var/www/ \
      -v /path/to/mysql:/var/lib/mysql \
      -p port_of_nginx:80 \ 
      stenote/docker-lemp:latest
      
## Container Usado
- https://github.com/stenote/docker-lemp

## Problemas encontrados:
O container está com o tamanho de upload limitado, com isso tive problemas para fazer upload através do wordpress então alterei o seguintes arquivos:

/etc/nginx/sites-enabled/default  

    server {
    listen 80;

    index index.php;
    client_max_body_size 100M; # Adicionei esta linha
    ...

/etc/php/7.0/cli/php.ini e /etc/php/7.0/fpm/php.ini  
neste alterei os seguintes parametros:    
    
    upload_max_filesize = 100M       
    post_max_size = 100M
