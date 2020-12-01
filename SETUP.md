# RESUMO

Instale o pipenv




# Ativação do virtualenv

Nós precisamos ativar o virtualenv para utilizar as bibliotecas instaladas pelo pipenv através do seguinte comando:

```
pipenv shell
```

Caso você queira executar algum comando dentro do virtualenv sem precisar ativar o virtualenv, utilize o seguinte comando:

```
pipenv run <comando>
```

Exemplo:

```
pipenv run python main.py
```

Se quisessemos listar as bibliotecas instaladas em nosso virtualenv antes mesmo de ativá-lo por exemplo:

```
pipenv run pip freeze
```

# Para instalar as bibliotecas do Projeto

Em um novo local, após baixar o projeto do Git faça:

```
pipenv install
```

# Gerando o Requirements pelo pipenv

```
pipenv lock --requirements > requirements.txt
```

Isto será útil no Dockerfile. Para não esquecermos de
atualizar o requirements.txt toda vez que formos gerar a
imagem vamos colocar este comando no Dockerfile.

```yml
FROM python:3.8.1-alpine

WORKDIR /backend

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONBUFFERED 1

RUN pip install pipenv
COPY Pipfile* /backend
RUN cd /backend && pipenv lock --requirements > requirements.txt

RUN set -eux \
  && apk add --no-cache --virtual .build-deps build-base \
     libressl-dev libffi-dev gcc musl-dev python3-dev \
     libc-dev libxslt-dev libxml2-dev bash \
     postgresql-dev \
  && pip install --upgrade pip setuptools wheel \
  && pip install -r /backend/requirements.txt \
  && rm -rf /root/.cache/pip

COPY . /backend
```
