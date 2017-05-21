FROM openjdk:8

RUN apk add --update ruby=2.3.1-r0 ruby-irb=2.3.1-r0 ruby-rdoc=2.3.1-r0 \
        ruby-io-console=2.3.1-r0 ruby-bigdecimal=2.3.1-r0 ruby-rake=2.3.1-r0 \
        && rm -rf /var/cache/apk/*

RUN gem install bundler -v 1.12.5
