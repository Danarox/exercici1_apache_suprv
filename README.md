Practica 1 amb imatge apache i supervisor 

Comanda per crear una imatge amb el dockerfile(arrel de carpeta):
docker build -t exercici1

Comanda per arrancar el contenidor:
docker run -itd -p 80:80 -p 8200:8200 -p 9001:9001 -e USER=danarox -e PASSWORD=Truger250 exercici1
 
Després fer un docker start [ID] imatge
