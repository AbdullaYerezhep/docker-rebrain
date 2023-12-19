FROM golang:1.19-alpine
WORKDIR /app
ARG SECRET_ARG
ENV GO111MODULE auto
RUN echo $SECRET_ARG > secret.txt

FROM alpine:3.10.3
WORKDIR /app
COPY --from=0 /app/secret.txt .
CMD ["cat", "secret.txt"]