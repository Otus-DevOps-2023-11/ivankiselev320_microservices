FROM ruby:2.4-slim

RUN apt-get update -qq && \
    apt-get install -y build-essential

ENV APP_HOME /app

RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME

COPY Gemfile* ./
RUN bundle install

COPY . .

ENV COMMENT_DATABASE_HOST comment_db
ENV COMMENT_DATABASE comments

CMD ["puma"]
