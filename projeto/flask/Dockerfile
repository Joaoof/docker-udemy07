FROM python:3

RUN apt-get update -y  && \
    apt-get install -y python3-pip python3-dev

WORKDIR /home/joao/Documentos/network-docker/2_host/app.py


RUN pip install flask
RUN pip install Flask requests
RUN pip install flask-mysqldb
RUN pip install pymysql




COPY . .

EXPOSE 5003

CMD [ "python", "./app.py" ]