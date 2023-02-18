# base image
FROM python:3.8-slim-buster

# set working directory
WORKDIR /app

# copy requirements file
COPY requirements.txt .

# install dependencies
RUN pip install -r requirements.txt

# copy project files
COPY . .

# set environment variables
ENV DJANGO_SETTINGS_MODULE=myproject.settings
ENV PYTHONUNBUFFERED=1

# run migrations
RUN python manage.py migrate

# expose port
EXPOSE 8000

# start the server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

