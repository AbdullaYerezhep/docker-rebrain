# Используем базовый образ ubuntu:18.04
FROM ubuntu:18.04

# Обновляем индексы пакетов и устанавливаем nginx
RUN apt-get update && \
    apt-get install -y nginx && \
    rm -rf /var/lib/apt/lists/*

# Копируем конфигурационный файл nginx
COPY nginx.conf /etc/nginx/nginx.conf

# Устанавливаем основную рабочую директорию
WORKDIR /etc/nginx/

# Определяем Volume с путем /var/lib/nginx
VOLUME /var/lib/nginx

# ENTRYPOINT для запуска nginx
ENTRYPOINT ["nginx"]

# CMD с параметрами запуска nginx
CMD ["-g", "daemon off;"]