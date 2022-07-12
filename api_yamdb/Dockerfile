FROM python:3.7-slim

WORKDIR /app

COPY api_yamdb/requirements.txt ./

RUN pip3 install -r requirements.txt --no-cache-dir

COPY ./ ./

WORKDIR api_yamdb/

RUN python3 manage.py collectstatic --no-input

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
