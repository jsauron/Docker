
#source : https://foxinou.fr/installer-serveur-teamspeak-3-linux-ts3/
#docker run -it --name ex01 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 30033:30033 -p 10011:10011 -p 41144:41144 --rm -it teamspeak
FROM debian

EXPOSE 9987/udp 30033 10011

RUN apt-get update \
	&& apt-get install wget bzip2 wget ca-certificates -y \
	&& adduser --disabled-password --gecos "" teamspeak

WORKDIR /home/teamspeak

RUN wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
	&& tar -xzvf *.tar.gz && rm *.tar.gz

WORKDIR teamspeak3-server_linux-amd64

CMD ["sh", "ts3server_minimal_runscript.sh"]
