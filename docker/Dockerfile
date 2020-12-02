FROM ruby:2.4.1

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN mkdir /api

WORKDIR /api
ADD api/Gemfile /api/Gemfile
ADD api/Gemfile.lock /api/Gemfile.lock
RUN gem install bundler
ADD /api /api
RUN cd api && bundle install && rails server