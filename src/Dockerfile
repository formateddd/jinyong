FROM ubuntu:latest
# COPY sources.list /etc/apt/sources.list
RUN apt update -y
RUN apt install python3 python3-pip -y

RUN mkdir /sockets
COPY . /app
WORKDIR /app
RUN pip3 install -r /app/requirements.txt
#-i http://pypi.douban.com/simple --trusted-host pypi.douban.com
CMD /usr/local/bin/uwsgi --ini /app/uwsgi.ini
# CMD /usr/local/bin/uwsgi --socket /sockets/uwsgi.sock --wsgi-file main.py --callable app --processes 4 --threads 2 -b 32768 
