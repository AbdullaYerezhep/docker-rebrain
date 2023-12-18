# Используем базовый образ nginx с параметризуемой версией
ARG NG_VERSION
FROM nginx:$NG_VERSION

# Устанавливаем переменную окружения с именем NG_VERSION
ENV NG_VERSION $NG_VERSION

# Создаем файл /opt/$ARG_FILE, где значение передается через ARG
ARG ARG_FILE
RUN touch /opt/$ARG_FILE

# Передача переменной окружения в контейнер при запуске
ENV REBRAINME DKR10