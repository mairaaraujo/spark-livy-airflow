FROM bde2020/spark-master:2.4.4-hadoop2.7

ENV SPARK_HOME /spark

RUN apk --no-cache add procps && \ 
    mkdir /livy && \
    cd /livy && \ 
    wget http://mirrors.estointernet.in/apache/incubator/livy/0.6.0-incubating/apache-livy-0.6.0-incubating-bin.zip && \
    unzip apache-livy-0.6.0-incubating-bin.zip  && \
    /spark/bin/spark-submit \
    --class thoughtworks.wordcount.WordCount \
    /job/tw-pipeline_2.11-0.1.0-SNAPSHOT.jar

    # ./bin/spark-submit \
    # --class thoughtworks.wordcount.WordCount \
    # --master yarn \
    # --deploy-mode cluster \
    # --executor-memory 20G \
    # /job/tw-pipeline_2.11-0.1.0-SNAPSHOT.jar 1000



ADD start.sh /

CMD ["sh", "/start.sh"]