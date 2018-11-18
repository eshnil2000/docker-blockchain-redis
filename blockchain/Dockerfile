FROM python:3.6-alpine

WORKDIR /app

ENV BUILD_LIST git
ENV REDIS_HOST localhost
ENV REDIS_PORT 6379
ADD blockchain.py Pipfile /app/
RUN pip install pipenv \
    && pipenv --python=python3.6 \
    && pipenv install \
    && rm -rf /var/cache/apk/*

EXPOSE 5000

ENTRYPOINT [ "pipenv", "run", "python", "/app/blockchain.py", "--port", "5000"  ]
