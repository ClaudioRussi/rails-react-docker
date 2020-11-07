FROM ruby:2.5
RUN apt-get update -qq && apt-get install -y nodejs postgresql-client
RUN mkdir /be
WORKDIR /be
COPY Gemfile /be/Gemfile
COPY Gemfile.lock /be/Gemfile.lock
RUN bundle install
COPY . /be

#add a script to execute when the container starts
COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT [ "entrypoint.sh" ]
EXPOSE 4000

#Start the main process
CMD ["rails", "server", "-p", "4000", "-b", "0.0.0.0"]