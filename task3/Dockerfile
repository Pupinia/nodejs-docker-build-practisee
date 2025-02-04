FROM node:16-alpine

# Задаем рабочую директорию
WORKDIR /home/ilovedocker/app


# установка зависимостей
# астериск ("*") по возможности скопирует оба файла: package.json и package-lock.json
# тот же символ делает копирование опциональным, т. е. без файла сборка не упадёт
COPY ./packages/package*.json ./
# Флаг --omit=dev означает - "не ставить devDependencies"
# они не нужны нам в продакшен-окружении
RUN npm i --omit=dev
# копируем исходный код
COPY ./src/* .

EXPOSE 3032
CMD [ "node", "main.js" ] 