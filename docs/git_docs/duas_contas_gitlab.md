# COMO GERENCIAR DUAS CONTAS GITLAB NO WINDOWS

Para conseguir trabalhar com duas ou mais contas do Gitlab no seu windows é preciso fazer uma configuração. 

No diretório docs/git_docs/configs_gitlab_duas_contas
temos os arquivos que devemos copiar para a raíz da pasta do seu usuário windows.

No arquivo docs/git_docs/configs_gitlab_duas_contas/.gitconfig temos a configuração global.

Que determina que o VSCode será utilizado como editor principal e também como ferramenta de diff local e global.

Veja que defini o diretório **work** para conter os projetos do trabalho. E as configurações específicas de chave ficam dentro do arquivo docs/git_docs/configs_gitlab_duas_contas/.gituser-ampere.

No arquivo também contém algumas personalizações de comandos para facilitar a visualização. 

Lembrando que você deve utilizar o terminal do Git for Windows para gerar
duas chaves com o comando:

```
ssh-keygen -t rsa
```

Daí salve as chaves em C:\Users\<Seu Usuário>\.ssh.

Neste caso temos as chaves id_rsa_pessoal conforme configurado
em docs/git_docs/configs_gitlab_duas_contas/.gituser-default:


```ini
[user]
	name = Marcelo Palin
	email = email@pessoal.com
[core]
	sshCommand = "ssh -i ~/.ssh/id_rsa_pessoal"
	editor = code --wait
[alias]
	c = !git add --all && git commit -m
	s = !git status -s 
	l = log --graph --decorate --date-order --date=local --date=format:'%y-%M-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cgreen(%cd) %C(auto)%d %C(bold blue)<%an>%Creset'  --max-count=10 --abbrev-commit 
```

E também id_rsa_work conforme configurado em docs/git_docs/configs_gitlab_duas_contas/.gituser-work


docs/git_docs/configs_gitlab_duas_contas/.gituser-work
```ini
[user]
	name = Marcelo Palin
	email = email@work.com
[core]
	sshCommand = "ssh -i ~/.ssh/id_rsa_work"
[alias]
	c = !git add --all && git commit -m
	s = !git status -s 
	l = log --graph --decorate --date-order --date=local --date=format:'%y-%M-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cgreen(%cd) %C(auto)%d %C(bold blue)<%an>%Creset'  --max-count=10 --abbrev-commit 
```


```ini
# This is Git's per-user configuration file.
[include]
  path = .gituser-default
[includeIf "gitdir:~/work/"]
  path = .gituser-work
[alias]
	c = !git add --all && git commit -m
	s = !git status -s 
	l = log --graph --decorate --date-order --date=local --date=format:'%y-%M-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cgreen(%cd) %C(auto)%d %C(bold blue)<%an>%Creset'  --max-count=10 --abbrev-commit 
	lall = log --graph --decorate --date-order --date=local --date=format:'%y-%M-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cgreen(%cd) %C(auto)%d %C(bold blue)<%an>%Creset' --abbrev-commit 

[core]
	autocrlf = input
	editor = code --wait
[user]
	name = Marcelo Palin
	email = email@work.com
# Add this to you gitconfig
# Comment: Start of "Extra Block"
# Comment: This is to unlock VSCode as your git diff and git merge tool
[merge]
    tool = vscode
[mergetool "vscode"]
    cmd = code --wait $MERGED
[diff]
    tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
# VSCode Difftool
## End of extra block
```

