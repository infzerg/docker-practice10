FROM python:3-11-slim

LABEL maintainer="biba i boba"
      description="2 dolboeba"
      version="1.0"

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    APP_VERSION=1.0.0 \
    ENVIRONMENT=prod

COPY requirements.txt

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        curl \
        wget \
        vim \
        git \
        build-essential \
    && pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY app.py .

RUN groupadd -g 1001 appgroup \
    && useradd -u 1001 -g appgroup -m appuser \
    && chown -R 1001:1001 /app

USER appuser

EXPOSE 8080

CMD ["python", "app.py"]
