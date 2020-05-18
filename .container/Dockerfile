FROM python:alpine

RUN mkdir /workspace
WORKDIR /workspace

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Web Installation
RUN apk update
# POSTGRESDB Dependencies
RUN apk add postgresql-dev gcc python3-dev musl-dev

RUN pip install --upgrade pip
COPY requirements.txt /workspace/requirements.txt
RUN pip install -r requirements.txt

COPY ./.container/.entrypoint.sh /workspace/.container/.entrypoint.sh
COPY . /workspace
ENTRYPOINT ["/workspace/.container/.entrypoint.sh"]
