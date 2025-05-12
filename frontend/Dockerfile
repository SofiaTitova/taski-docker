# Используем официальный образ Node.js
FROM node:18

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файлы зависимостей
COPY package.json package.json
COPY package-lock.json package-lock.json

# Устанавливаем зависимости
RUN npm install

# Копируем весь проект
COPY . .

# Собираем фронтенд
RUN npm run build

# Запускаем сервер, который будет отдавать статику из build
CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
