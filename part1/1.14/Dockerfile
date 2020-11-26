FROM ruby:2.6.0

ARG SECRET_KEY_BASE=change_this
ENV SECRET_KEY_BASE=$SECRET_KEY_BASE
WORKDIR /myapp
COPY ./rails-example-project-master /myapp
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash
RUN apt-get update && apt-get install -y nodejs
RUN gem install bundler
RUN bundle install
RUN SECRET_KEY_BASE=$SECRET_KEY_BASE rails db:migrate RAILS_ENV=production 
RUN rake assets:precompile
EXPOSE 3000
CMD rails s -e production
