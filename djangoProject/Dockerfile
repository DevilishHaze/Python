# Используем базовый образ Python 3.10
FROM python:3.11

# Устанавливаем переменные среды
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем зависимости (файл requirements.txt) внутрь контейнера
COPY requirements.txt /app/

# Устанавливаем зависимости
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN mkdir -p /app/static /app/media/images
# Копируем все остальные файлы проекта внутрь контейнера
COPY . /app/

# Запускаем команду, которая будет запускать Django приложение
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
