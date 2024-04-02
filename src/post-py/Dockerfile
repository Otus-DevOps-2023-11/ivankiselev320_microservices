FROM python:3.6.0-alpine

RUN apk --no-cache --update add build-base

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir -r requirements.txt

RUN apk del build-base

ENV POST_DATABASE_HOST post_db
ENV POST_DATABASE posts

ENTRYPOINT ["python3", "post_app.py"]
