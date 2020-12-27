FROM python:3.8

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

RUN echo "deb http://mirrors.aliyun.com/debian/ jessie main non-free contrib \
deb http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib \
deb-src http://mirrors.aliyun.com/debian/ jessie main non-free contrib \
deb-src http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib" > /etc/apt/sources.list \
	&& apt-get update \
	&& apt-get install -y supervisor

RUN mkdir /etc/scrapyd && mkdir /root/logs

ADD ./scrapyd.conf /etc/scrapyd/scrapyd.conf

ADD ./supervisord.conf /etc/supervisor/conf.d

ADD requirements.txt /opt/requirements.txt

WORKDIR /opt

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U \ 
&&  pip install -U git+https://github.com/scrapy/scrapyd.git \
&& pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt 

CMD supervisord




