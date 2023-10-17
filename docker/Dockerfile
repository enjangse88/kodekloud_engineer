FROM ubuntu
ARG DEBIAN=noninteractive
RUN apt update
RUN apt install -y apache2
RUN sed -i 's/Listen 80/Listen 5002/g' /etc/apache2/ports.conf
CMD ["apachectl","-DFOREGROUND"]
EXPOSE 5002