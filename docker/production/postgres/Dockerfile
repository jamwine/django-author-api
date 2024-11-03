FROM postgres:15-bullseye


COPY ./docker/production/postgres/maintenance /usr/production/bin/maintenance

RUN chmod +x /usr/production/bin/maintenance/*

# convert line endings to unix
RUN find /usr/production/bin/maintenance -type f -exec sed -i 's/\r$//g' {} +

# Move scripts
RUN mv /usr/production/bin/maintenance/* /usr/production/bin \
  && rmdir /usr/production/bin/maintenance
