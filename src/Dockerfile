FROM python:3.11-slim-bluster

RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip

COPY . /code

RUN chmod +x /codec/src

RUN pip install --no-cache-dir --upgrade -r code/src/requirements.txt

EXPOSE 8005

WORKDIR /code/src

ENV PYTHONPATH "${PYTHONPATH}:/code/src"

CMD pip install -e .