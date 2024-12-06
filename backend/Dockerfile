FROM python:3.10

ENV PYTHONUNBUFFERED=1

WORKDIR /app/

COPY requirements.txt /app/

RUN pip install -r requirements.txt

ENV PYTHONPATH=/app

COPY ./scripts /app/scripts

COPY ./pyproject.toml ./uv.lock ./alembic.ini /app/

COPY ./app /app/app

CMD ["sh", "./scripts/prestart_gunicorn.sh"]