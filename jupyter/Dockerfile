FROM python:2.7.15-alpine3.6
MAINTAINER panzhengming@juxinli.com
RUN mkdir /root/.pip -p && \
    mkdir /opt/app -p && \
        sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
ADD pip.conf /root/.pip/pip.conf
RUN apk add --no-cache musl-dev gcc build-base
RUN pip install --no-cache jupyter
WORKDIR /opt/app
VOLUME [ "/opt/app" ]
EXPOSE 8888
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--allow-root"]
