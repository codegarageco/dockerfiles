FROM faizalzakaria/ruby-2.3.1:latest
MAINTAINER Faizal Zakaria

RUN gem install mailcatcher

EXPOSE 1080
EXPOSE 1025

CMD ["--smtp-port", "1025", "--http-port", "1080", "--ip", "0.0.0.0", "-f"]
ENTRYPOINT ["mailcatcher"]
