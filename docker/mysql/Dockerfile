FROM mysql:5.7.22

# Копируем общие скрипты
COPY ./shared/ /tmp/scripts/
RUN chmod +x -R /tmp/scripts/

# Копирует скрипт для заливки баз данных
COPY ./mysql/init/init.sh /opt/mysql/init.sh
RUN chmod +x /opt/mysql/init.sh

# Устанавливаем полезные утилиты
RUN /tmp/scripts/install_software.sh

# Установка TIMEZONE
ARG TIMEZONE
RUN /tmp/scripts/install_timezone.sh ${TIMEZONE}