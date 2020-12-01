Execute com o ambiente ativado:

pipenv shell

e se for em uma nova pasta faça a instalação dos pacotes:

pipenv install [package names]
The user can provide these additional parameters:

--two — Performs the installation in a virtualenv using the system python2 link.
--three — Performs the installation in a virtualenv using the system python3 link.
--python — Performs the installation in a virtualenv using the provided Python interpreter.
Warning
None of the above commands should be used together. They are also destructive and will delete your current virtualenv before replacing it with an appropriately versioned one.

Note
The virtualenv created by Pipenv may be different from what you were expecting. Dangerous characters (i.e. $`!*@" as well as space, line feed, carriage return, and tab) are converted to underscores. Additionally, the full path to the current folder is encoded into a “slug value” and appended to ensure the virtualenv name is unique.

--dev — Install both develop and default packages from Pipfile.
--system — Use the system pip command rather than the one from your virtualenv.
--deploy — Make sure the packages are properly locked in Pipfile.lock, and abort if the lock file is out-of-date.
--ignore-pipfile — Ignore the Pipfile and install from the Pipfile.lock.
--skip-lock — Ignore the Pipfile.lock and install from the Pipfile. In addition, do not write out a Pipfile.lock reflecting changes to the Pipfile.

Comando utilizado:

```
pipenv install --dev
```

```
pre-commit run --all-files -v
```

Rode duas vezes caso necessário para consertar os arquivos.

Em seguida faça o git add . antes de fazer um novo git commit
