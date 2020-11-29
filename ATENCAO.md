# Sempre que modificar o .pre-commit-config.yaml

Não esqueça de atualizar os hooks no diretório .git

Sempre rode o comando e corrija os problemas

```
pre-commit autoupdate
```

Saída:

```
Updating https://github.com/ambv/black ... already up to date.
Updating https://gitlab.com/pycqa/flake8 ... [INFO] Initializing environment for https://gitlab.com/pycqa/flake8.
updating 3.7.9 -> 3.8.4.
Updating git://github.com/pre-commit/pre-commit-hooks ... already up to date.
```

Depois rode manualmente o pre-commit:

```
pre-commit run --all-files -v
```
