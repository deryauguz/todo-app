FROM python:3.12-slim

WORKDIR /app

COPY app/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app/ .

RUN mkdir -p /data

ENV DB_PATH=/data/todo.db

EXPOSE 8080

CMD ["gunicorn", "-b", "0.0.0.0:8080", "app:app"]