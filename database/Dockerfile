
FROM mysql:8.4 AS builder

WORKDIR /app

COPY ./sql/physical_model.mysql /docker-entrypoint-initdb.d/physical_model.sql


FROM mysql:8.4 AS production

COPY --from=builder /docker-entrypoint-initdb.d/physical_model.sql \
    /docker-entrypoint-initdb.d/physical_model.sql
