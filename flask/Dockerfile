FROM ubuntu:latest

RUN apt-get update && apt-get install -y python3-dev python3-pip nginx && rm /etc/nginx/sites-enabled/default
ADD app /app
ADD flask /etc/nginx/sites-enabled

WORKDIR /app
RUN pip3 install -r requirements.txt

CMD service nginx restart; uwsgi --ini /app/flask.ini
