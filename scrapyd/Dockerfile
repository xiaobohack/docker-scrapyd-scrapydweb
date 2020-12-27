FROM python:3.8
MAINTAINER xiaobohack
ADD . /code
WORKDIR /code
COPY ./scrapyd.conf /etc/scrapyd/
RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U \ 
&& pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirement.txt 
CMD scrapyd