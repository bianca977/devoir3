FROM python:latest

#on definit les differentes variables d'environnement 

ENV POSTGRES_USER user
ENV POSTGRES_PASSWORD password
ENV POSTGRES_DB database
ENV CSV_FILENAME=data.csv



RUN wget https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh -P /
RUN chmod +x /wait-for-it.sh
ENTRYPOINT ["/wait-for-it.sh", "db:5432", "--"]

#on installe psycopg2 

RUN pip3 install psycopg2

EXPOSE 80

#on copie le contenu de manager dans un dossier nommé package

ADD . /package


CMD python -m package
