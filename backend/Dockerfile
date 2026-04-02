FROM python:3.12

WORKDIR /app

RUN pip install gunicorn==23.0.0

COPY requirements.txt .

# Используем официальное зеркало для стабильной загрузки
RUN pip install --upgrade pip && \
    pip install -r requirements.txt --no-cache-dir \
    -i https://mirrors.aliyun.com/pypi/simple/ \
    --trusted-host mirrors.aliyun.com

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
