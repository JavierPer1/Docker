FROM bde2020/hadoop-base:2.0.0-hadoop3.2.1-java8

# Instalar Hive
RUN wget http://apache.rediris.es/hive/hive-2.3.4/apache-hive-2.3.4-bin.tar.gz && \
    tar xvf apache-hive-2.3.4-bin.tar.gz && \
    mv apache-hive-2.3.4-bin /usr/local/hive && \
    rm apache-hive-2.3.4-bin.tar.gz

# Configurar variables de entorno
ENV HIVE_HOME=/usr/local/hive
ENV PATH=$PATH:/usr/local/hive/bin

# Copiar archivos de configuración
COPY config/hive-site.xml /usr/local/hive/conf/hive-site.xml

# Comando de inicio
CMD ["hive"]

FROM bde2020/hadoop-namenode:2.0.0-hadoop2.7.4-java8 
COPY docker-compose.yml /app/ 
WORKDIR /app
 