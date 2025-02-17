FROM python:3.12-slim as builder

WORKDIR /app

COPY requirements.txt .

RUN pip --no-cache-dir upgrade -y && pip install --no-cache-dir install -r requirements.txt --target /dependencies


FROM python:3.12-alpine as builder

WORKDIR /app

COPY . .

COPY --from=builder /dependencies /usr/local

CMD ["python", "app.py"]


