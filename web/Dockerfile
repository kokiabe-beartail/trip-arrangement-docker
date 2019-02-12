FROM ruby:2.5.0

# set environment variables
ENV LANG C.UTF-8
ENV ROOT_PATH /app

# install essential libraries
RUN apt-get update && apt-get install -y build-essential libpq-dev postgresql-client

# install node.js
RUN curl -sL https://deb.nodesource.com/setup_7.x | bash - && \
    apt-get install nodejs

# install yarn
RUN apt-get update && apt-get install -y curl apt-transport-https wget && \
    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn


# move to root
RUN mkdir $ROOT_PATH
WORKDIR $ROOT_PATH

RUN gem install rails
