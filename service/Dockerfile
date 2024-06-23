FROM python:3.12

WORKDIR /opt/link_dst/service
COPY requirements.txt requirements.txt

RUN chmod +x .

RUN chmod +x .
RUN  pip install --index-url=https://pypi.python.org/simple/ --trusted-host pypi.python.org --upgrade pip \
     && pip install --index-url=https://pypi.python.org/simple/ --trusted-host pypi.python.org --no-cache-dir -r requirements.txt

COPY . .
