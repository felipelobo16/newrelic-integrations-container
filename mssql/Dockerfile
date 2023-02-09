FROM golang:1.18 as go-builder
ENV CGO_ENABLED=0
ENV GOOS=linux
WORKDIR /work
RUN git clone https://github.com/newrelic/nri-mssql.git .
RUN make clean compile

FROM newrelic/infrastructure:latest
COPY --from=go-builder /work/bin/nri-mssql /var/db/newrelic-infra/newrelic-integrations/bin

COPY ./integrations /etc/newrelic-infra/integrations.d

ENV NRIA_IS_FORWARD_ONLY=true \
    NRIA_K8S_INTEGRATION=true \
    NRIA_LOG_LEVEL=info \
    NRIA_LICENSE_KEY=your_key

RUN apk update