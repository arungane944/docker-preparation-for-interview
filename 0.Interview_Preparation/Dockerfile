# write multistage docker file

FROM python:3.8-slim as builder

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir --upgrade pip && \
    pip install  --no-cache-dir -r requirements.txt --target=/dependencies


    
FROM python:3.8-alpine


WORKDIR /app

COPY --from=builder /dependencies /usr/local/lib/python3.8/site-packages

COPY . .

CMD ["python", "app.py"]