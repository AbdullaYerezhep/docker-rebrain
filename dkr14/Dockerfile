    FROM golang:1.19-alpine AS builder
    WORKDIR /app
    COPY main.go .
    ENV GO111MODULE auto
    RUN go mod init main && \
        go mod tidy && \
        go build -o app
    
    FROM alpine:3.10.3
    WORKDIR /app
    COPY --from=builder /app/app .
    CMD ["./app"]