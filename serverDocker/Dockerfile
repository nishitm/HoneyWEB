#FROM debian:latest

FROM r0hi7/nodejs

MAINTAINER Rohit Sehgal (rsehgal@iitk.ac.in)

#RUN apt-get update -y && apt-get install --no-install-recommends -y -q curl python build-essential git ca-certificates
#RUN mkdir /nodejs && curl http://nodejs.org/dist/v0.10.30/node-v0.10.30-linux-x64.tar.gz | tar xvzf - -C /nodejs --strip-components=1

#ENV PATH $PATH:/nodejs/bin


#RUN apt-get install build-essential httrack -y
#RUN apt-get install supervisor -y

#RUN mkdir -p /home/httrack/

#RUN httrack $URL -O /home/httrack/

#RUN npm install -g static-server
#COPY superbisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN apt-get update && apt-get install php5 php5-mysql php5-fpm php5-json php5-cgi -y

RUN mkdir -p /app/server/cse.iitk.ac.in
WORKDIR /app/server
ADD package.json /app/server
RUN npm install
#ADD cse.iitk.ac.in/cse.iitk.ac.in /app/server/cse.iitk.ac.in
ADD server.js /app/server/server.js
EXPOSE 80

ENTRYPOINT ["npm","start"]
#ENTRYPOINT ["echo"]
#CMD [$URL]
#,"-O","/home/httrack/","-r5"]

