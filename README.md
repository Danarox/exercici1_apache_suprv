## Practica 1 amb imatge apache i supervisor
Comanda per crear una imatge amb el dockerfile(arrel de carpeta):
````
docker build -t exercici1
````
Comanda per arrancar el contenidor:
````
docker run -itd -p 80:80 -p 8200:8200 -p 9001:9001 -e USER=danarox -e PASSWORD=Truger250 exercici1
````
Després fer un docker start [ID] imatge
        
## Practica 2 docker-compose.yml
        
Comanda per executar docker-compose
````docker-compose up -d````
Si sorgeix algun error al instalar worpress a traves del compose es que no s'ha aplicat correctament
Si cal aplicar configuració manual: Entrem al contenidor de apache les comandes per instalar wordpress    
````
cd /var/www/html
yum install -y wget
wget https://wordpress.org/latest.tar.gz 
tar -xvf latest.tar.gz 
rm -f latest.tar.gz 
mv var/www/html/wordpress/* /var/www/html
rm -rf /var/www/html/wordpress 
chown -R apache:apache /var/www/html 
chmod -R 755 /var/www/html
````
Entrem al contenidor de mariadb per crear la bd de wordpress:
````
mysql -uroot -piaw
create database wordpres;
CREATE USER 'danarox' IDENTIFIED BY 'Truger250';
GRANT USAGE ON *.* TO 'danarox'@localhost IDENTIFIED BY 'Truger250';
GRANT USAGE ON *.* TO 'danarox'@'%' IDENTIFIED BY 'Truger250';
