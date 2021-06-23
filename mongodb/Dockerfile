FROM apache/zeppelin:0.9.0
USER root
RUN useradd -M zeppelin
# takes a long time
RUN chown -R zeppelin /opt/zeppelin && mkdir -p /home/zeppelin && chown -R zeppelin /home/zeppelin
WORKDIR /opt
RUN wget https://downloads.mongodb.com/compass/mongosh-0.15.1-linux-x64.tgz
RUN tar xfv mongosh-0.15.1-linux-x64.tgz && \
    rm mongosh-0.15.1-linux-x64.tgz && \
    chown -R zeppelin mongosh-0.15.1-linux-x64 && \
    ln -s /opt/mongosh-0.15.1-linux-x64/bin/mongosh /usr/bin/mongo && \
    chown zeppelin /usr/bin/mongo

USER zeppelin
WORKDIR /opt/zeppelin
