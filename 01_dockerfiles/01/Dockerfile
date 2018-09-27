FROM debian:latest

#source : https://foxinou.fr/installer-serveur-teamspeak-3-linux-ts3/
#docker run -it --name ex01 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 30033:30033 -p 10011:10011 -p 41144:41144 --rm -it teamspeak

RUN useradd teamspeak && su teamspeak

RUN apt-get update && apt-get install -y 
	&& cd /home/teamspeak
	&& wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz 
	&& tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
	&& rm teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
	&& cd  teamspeak3-server_linux-amd64 \

EXPOSE 9987/udp  10011  30033 41144 

CMD ["ts3server_minimal_runscript.sh", "createinifile=1"]

./ts3server_startscript.sh start

