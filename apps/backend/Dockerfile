FROM python:3.9-slim

WORKDIR /app
COPY requirements.txt .

ARG ENV=production
ENV ENV=${ENV}

RUN pip install --default-timeout=100 -r requirements.txt

COPY . .

CMD if [ "$ENV" = "production" ]; then \
    uvicorn main:app --host 0.0.0.0 --port 8000; \
    else \
    uvicorn main:app --host 0.0.0.0 --port 8000 --reload; \
    fi