FROM python:3.11-slim

ENV PYTHONUNBUFFERED 1

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY app.py app.py