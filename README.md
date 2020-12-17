# 1. Fast API

FastAPI é um moderno e rápido (alta performance) framework web para construção de APIs com Python 3.6 ou superior, baseado nos type hints padrões do Python.

Os recursos chave são:

- Rápido: alta performance, equivalente a NodeJS e Go (graças ao Starlette e Pydantic). Um dos frameworks mais rápidos disponíveis.

- Rápido para codar: Aumenta a velocidade para desenvolver recursos entre 200% a 300%. *

- Poucos bugs: Reduz cerca de 40% de erros induzidos por humanos (desenvolvedores). *

- Intuitivo: Grande suporte a IDEs. Auto-Complete em todos os lugares. Menos tempo debugando.

- Fácil: Projetado para ser fácil de aprender e usar. Menos tempo lendo documentação.

- Enxuto: Minimize duplicação de código. Múltiplos recursos para cada declaração de parâmetro. Menos bugs.

- Robusto: Tenha código pronto para produção. E com documentação interativa automática.

- Baseado em padrões: Baseado em (e totalmente compatível com) os padrões abertos para APIs: OpenAPI (anteriormente conhecido como Swagger) e JSON Schema.


Obs: existem excelentes projetos já prontos que já integram FastApi com Vuejs com Celery, Postgres que você encontra
em https://fastapi.tiangolo.com/project-generation/

Estudar o formato: https://fastapi.tiangolo.com/project-generation/

# 2. SETUP

O pipenv foi adotado como ambiente virtual do projeto.

Caso não conheça:

O pipenv é uma ferramenta completa para o gerenciamento de dependências em projetos Python, unindo Pipfile, pip e virtualenv em uma única ferramenta. Ele cria automaticamente o virtualenv e gerencia as suas dependências.

As principais vantagens de utilizar pipenv são:

- Gerenciamento de dependências por grupos igual ao node. (separa as dependências padrão e de desenvolvimento, em breve poderá personalizáveis).
- Possibilita a verificação de versão do python ou sistema operacional.
- Adiciona no Pipfile as dependências instaladas e retira as desinstaladas automaticamente.
- Encontra o Pipfile recursivamente dentro do projeto, permitindo a instalação de dependências à partir de qualquer localização dentro do projeto.

O Pipenv combina ambientes pip e virtuais em uma única ferramenta que gerencia as dependências do projeto de maneira determinística. Você pode instalar isso via pip.

Este projeto inicial vem com as seguintes dependências de desenvolvimento:

Pytest, pre-commit e mypy.

Instalando Pipenv é indicado usarmos o Pipx

```
python3 -m pip install --user pipx
```
```
pipenv shell
```

Então o arquivo Pipfile foi criado:

```ini
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]

[requires]
python_version = "3.8"
```

Agora você verá que ele criou e ativou o ambiente virtual e se der o comando **pip list**
você verá que o ambiente só possui 3 pacotes instalados:

```
Package    Version
---------- -------
pip        20.2.4
setuptools 50.3.2
wheel      0.35.1
```
Seu prompt indica que o ambiente virtual está ativado:

(fast_api_tutorial) mpi@DESKTOP-4DUQ19F:~/projs_python/tutoriais/fast_api_tutorial$


# 3. Adicionando os Pacotes com Pipenv

Instalando os pacotes apenas para desenvolvimento

```
pipenv install --dev pre-commit
pipenv install --dev pytest
pipenv install --dev mypy
```

# Para instalar as bibliotecas do Projeto

Em um novo local, após baixar o projeto do Git faça:

```
pipenv install
```

# 4. References

## 4.1. FastAPI

https://fastapi.tiangolo.com/


## 4.2. GraphQL Topic

https://fastapi.tiangolo.com/advanced/graphql/


## Pipenv

https://medium.com/code-rocket-blog/gerenciando-suas-depend%C3%AAncias-e-ambientes-python-com-pipenv-9e5413513fa6

https://medium.com/@patrickporto/introdu%C3%A7%C3%A3o-ao-pipenv-49aa9685dfe4



## 4.3. FastAPI Third party extensions

https://github.com/mjhea0/awesome-fastapi#third-party-extensions

- https://github.com/frankie567/fastapi-users
- https://github.com/mfreeborn/fastapi-sqlalchemy

## 4.4. Blogs

https://www.jeffastor.com/blog/up-and-running-with-fastapi-and-docker


## 4.5. Pydantic

https://medium.com/better-programming/the-beginners-guide-to-pydantic-ba33b26cde89


## 4.6. Git and GitHub

https://balta.io/blog/git-github-primeiros-passos


## 4.7. YOUTUBE

https://www.youtube.com/watch?v=Qh3iVePzrEU&list=UUkBbd1D04_yGaxEYbBKKFVg&index=5


# 5. OTHERS

Construindo webhook com FastAPI

https://www.twilio.com/blog/construindo-twilio-webhook-seguro-python-fastapi


Exemplo cria API com Poetry, JWT, SQLAlchemy com MySQL e Bcrypt (Usa o Pipfile)

https://codeburst.io/implement-a-production-ready-rest-service-using-fastapi-13f284562c75

Pipfile e Graphene

https://codeburst.io/implement-production-ready-graphql-server-with-graphene-a8a4547ceb20

Basico de Pytest (Veja video da Live https://www.youtube.com/watch?v=MxlS5_MI_WY)
https://giovannireisnunes.wordpress.com/2018/09/14/um-basico-de-pytest/

https://giovannireisnunes.wordpress.com/2020/09/25/utilizando-o-fastapi-parte-4/

YOUTUBE

https://www.youtube.com/watch?v=gVymPpepQco

Exemplo apenas de como configura o SQLAlchemy

https://www.youtube.com/watch?v=HVZUJb1_Jm8

Live
https://www.youtube.com/watch?v=MxlS5_MI_WY

# 6. Examples

PROJETOS QUE ENCONTREI NO GITHUB

https://github.com/nsidnev/fastapi-realworld-example-app

## 6.1. VARIOS EXEMPLOS

https://github.com/oinsd/FastAPI-Learning-Example

https://github.com/mfreeborn/fastapi-sqlalchemy

Busca no GITHUB https://github.com/search?p=2&q=fastapi&type=Repositories
