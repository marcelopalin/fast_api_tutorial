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

Depois rode manualmente o pre-commit duas vezes:

```
pre-commit run --all-files -v
```

A primeira mostra onde ocorreram as falhas.. a segunda vez o testes passam
pois foi corrigido.

```
(fast_api_tutorial) mpi@DESKTOP-4DUQ19F:~/projs_python/tutoriais/fast_api_tutorial$ pre-commit run --all-files -v
[WARNING] Unexpected key(s) present on https://github.com/pre-commit/mirrors-autopep8: entry, exclude, language, name
black................................................(no files to check)Skipped
- hook id: black
flake8...............................................(no files to check)Skipped
- hook id: flake8
autopep8.............................................(no files to check)Skipped
- hook id: autopep8
autopep8-unit-tests..................................(no files to check)Skipped
- hook id: autopep8
Trim Trailing Whitespace.................................................Passed
- hook id: trailing-whitespace
- duration: 0.07s
Fix End of Files.........................................................Passed
- hook id: end-of-file-fixer
- duration: 0.06s
Mixed line ending........................................................Passed
- hook id: mixed-line-ending
- duration: 0.07s
Check python ast.....................................(no files to check)Skipped
- hook id: check-ast
Fix python encoding pragma...........................(no files to check)Skipped
- hook id: fix-encoding-pragma
Fix requirements.txt.................................(no files to check)Skipped
- hook id: requirements-txt-fixer
Check for added large files..............................................Passed
- hook id: check-added-large-files
- duration: 0.22s
Check pytest unit tests pass.........................(no files to check)Skipped
- hook id: pytest
Check mypy static types match........................(no files to check)Skipped
- hook id: mypy
```
