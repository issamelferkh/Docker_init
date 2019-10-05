FROM ruby

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

RUN apt-get update -y && \
	apt-get install -y sqlite3 nodejs ruby-dev  && \
	gem update && \
	gem install bundler rails

ONBUILD	COPY app /opt/app
ONBUILD WORKDIR /opt/app/

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN bin/rake db:migrate
ONBUILD RUN bin/rake db:seed

# To build it.
# docker build -t ft-rails:on-build .