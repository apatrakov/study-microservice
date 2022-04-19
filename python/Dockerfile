FROM python:3.9-slim-bullseye as dev
ARG APP_DIR=/app

RUN apt update && apt-get install -y cron

WORKDIR /app

COPY ./app.py ./
COPY ./requirements.txt ./

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 8080

#ENTRYPOINT ["python -V"]
CMD ["python", "app.py"]