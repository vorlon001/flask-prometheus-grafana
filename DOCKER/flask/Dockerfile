from python:3.9-slim


COPY ./requirements.txt /tmp/requirements.txt

RUN apt-get update && \
    python -m pip install -r /tmp/requirements.txt && \
    /usr/local/bin/python -m pip install --upgrade pip && \
    rm -r /root/.cache/pip && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/* && \
    rm /tmp/requirements.txt

WORKDIR /app
COPY app.py ./app.py

CMD [ "python", "./app.py" ]
