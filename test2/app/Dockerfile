FROM python:3.7-alpine
WORKDIR /test2
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0

EXPOSE 5000
RUN pip install -U setuptools
RUN apk add --no-cache gcc musl-dev linux-headers

RUN pip install flask
RUN pip install sqlalchemy
RUN apk update && \
    apk add --virtual build-deps gcc python-dev musl-dev && \
    apk add postgresql-dev

RUN pip install psycopg2


COPY . .
CMD ["flask", "run"]
