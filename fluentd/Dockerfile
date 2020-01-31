FROM fluent/fluentd:v1.9-1
USER root
RUN apk add --update --virtual .build-deps \
    sudo build-base ruby-dev
RUN sudo gem install \
    fluent-plugin-elasticsearch fluent-plugin-concat \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* \
    /home/fluent/.gem/ruby/2.3.0/cache/*.gem
RUN mkdir -p /logs/myapp
# USER fluent
