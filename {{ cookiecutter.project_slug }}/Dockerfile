FROM python:3.12
LABEL authors="{{ cookiecutter.author }}"

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update && apt-get install --no-install-recommends -y \
  # dependencies for building Python packages
  build-essential

# set work directory
WORKDIR /app

COPY ./requirements.txt .

RUN pip install --upgrade pip
RUN pip install -r ./requirements.txt

COPY src .

ENTRYPOINT [ "python", "main.py" ]
