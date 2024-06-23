FROM python:3.12

WORKDIR /opt/link_dst/admin

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV UWSGI_PROCESSES 1
ENV UWSGI_THREADS 16
ENV UWSGI_HARAKIRI 240
ENV DJANGO_SETTINGS_MODULE 'config.settings'


COPY run.sh run.sh
COPY requirements.txt requirements.txt
COPY uwsgi/uwsgi.ini uwsgi.ini

RUN chmod +x .
RUN  pip install --index-url=https://pypi.python.org/simple/ --trusted-host pypi.python.org --upgrade pip \
     && pip install --index-url=https://pypi.python.org/simple/ --trusted-host pypi.python.org --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

ENTRYPOINT ["/opt/link_dst/admin/run.sh"]