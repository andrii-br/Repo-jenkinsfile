FROM python:3.10-alpine

WORKDIR /app

RUN pip install fastapi uvicorn

COPY . /app/

EXPOSE 8000:8000

CMD [ "python", "/app/app.py" ]