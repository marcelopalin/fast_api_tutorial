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
