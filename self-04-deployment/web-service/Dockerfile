FROM python:3.9.16-slim

RUN pip install -U pip
RUN pip install pipenv

WORKDIR /app

COPY ["Pipfile","Pipfile.lock", "./"]

RUN pipenv install --system --deploy

COPY ["lin_reg.bin","predict.py","./"]

EXPOSE 9696

ENTRYPOINT [ "gunicorn","--bind=0.0.0.0:9696", "predict:app" ]


