FROM node:12 as build



ENV LANG ja_JP.UTF-8
ENV LC_CTYPE ja_JP.UTF-8


RUN set -x && \
    apt-get update -y && \
    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apt-get install locales -y && locale-gen ja_JP.UTF-8 && localedef -f UTF-8 -i ja_JP ja_JP.utf8


# copy all file in treejs to ./
#COPY ./treejs ./
# copy dir [treejs] to ./
COPY treejs ./treejs
COPY locale.conf /etc/locale.conf

# if dont exist, create
WORKDIR /treejs


RUN npm install
# 本番用にコードを作成している場合
#RUN npm install --only=production

#EXPOSE 443

#CMD ["index.js"]
#CMD [ "node", "app.js" ]
#CMD [ "node", "bin/www" ]
#ENTRYPOINT ["ng", "serve", "-H", "0.0.0.0"]
CMD [ "npm", "start" ]







#WORKDIR /root

#COPY requirements.txt /requirements.txt

# base enviroment
#RUN set -x && \
#    yum update -y && \
#    yum install -y initscripts && \
#    yum install -y https://centos7.iuscommunity.org/ius-release.rpm && \
#    yum install -y python36u python36u-devel python36u-libs python36u-pip --enablerepo=ius && \
#    yum install -y python36u-tkinter --enablerepo=ius && \
#    yum install -y cronie && \
#    yum install -y systemd && \
#    yum install -y gcc gcc-c++ && \
#    yum install -y which patch file && \
#    yum -y install glibc-common && \
#    yum install -y supervisor && \
#    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
#    localedef -f UTF-8 -i ja_JP ja_JP
#
## projecr rely
#RUN set -x && \
#    python3 -m pip install --upgrade pip && \
#    echo 'alias python="/usr/bin/python3"' >> /root/.bashrc && \
#    echo 'alias pip="/usr/bin/pip3"' >> /root/.bashrc && \
#    pip install -r /requirements.txt
#
#WORKDIR /root
#
#COPY ius.repo /etc/yum.repos.d/ius.repo
#COPY locale.conf /etc/locale.conf
#COPY supervisor_crawl.ini /etc/supervisord.d/supervisor_crawl.ini
#COPY pricegetter_dev.conf /opt/kcc/conf/pricegetter.conf
#COPY etc/ /etc/
#COPY online_shop /opt/kcc/crawler/
#RUN chmod 644 /etc/cron.d/crawler
#
#CMD ["/usr/bin/supervisord", "-n"]

#CMD [ "node", "server.js" ]
