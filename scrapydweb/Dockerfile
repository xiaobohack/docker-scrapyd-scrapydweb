FROM python:3.8
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone
RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U \ 
&& pip install -i https://pypi.tuna.tsinghua.edu.cn/simple scrapydweb

COPY . /code

WORKDIR /code

CMD scrapydweb
