FROM ruby

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# Build it?
# docker build -t d_rails:on-build .