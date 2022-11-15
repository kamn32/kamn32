FROM python:3.9-slim

WORKDIR /src

ADD ./ /src/
RUN apt-get update
RUN pip install --upgrade pip
RUN apt-get install -y gcc
RUN pip install -r requirements.txt

# RUN mkdir db
# RUN chmod 777 db
# RUN python manage.py collectstatic
# RUN python manage.py migrate
# RUN chmod 777 ./db/db.sqlite3
RUN useradd -r -s /bin/false uwsgiusr
USER uwsgiusr
ENTRYPOINT ["uwsgi","--ini","/src/uwsgi.ini"]
