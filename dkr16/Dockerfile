    FROM golang:1.19-alpine AS builder
    WORKDIR /go/src/github.com/grafana/grafana
    RUN git clone --branch v6.3.x --depth 1 https://github.com/grafana/grafana.git .
    RUN go run build.go setup
    RUN go run build.go build
    
    FROM nginx:alpine
    WORKDIR /usr/share/nginx/html
    COPY --from=builder /go/src/github.com/grafana/grafana/public/ .
    
    
    EXPOSE 80
    
    # Start nginx
    CMD ["nginx", "-g", "daemon off;"]