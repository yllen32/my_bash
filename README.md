# my_bash
Полезные скрипты

```make
serve:
	python -m http.server dist --bind $(bind) $(port)
 #####################################
Запускаем с параметрами:

$ make serve bind=localhost port=3000
##############################
Можно указать значения по умолчанию:
bind ?= localhost
port ?= 3000
serve:
	python -m http.server dist --bind $(bind) $(port)
```


Зайти в каждую папку, прочесть все файлы info и перенаправить вывод в один файл.

```sh
 for dir in *; do (cd "$dir" && cat info.txt >> /f/m/total.txt && printf "\n-----" >> /f/m/total.txt); done
 ```

### псевдонимы для git

```bash
[core]
        autocrlf = input
[alias]
        co=checkout
        ci=commit
        di=diff
        st=status
        br=branch
        lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
        lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
        lg = !"git lg1"
```

```bash
git fetch --all # скопировать все изменения с удалённого репозитория
git fetch --prune # оббновить ссылки на ветки
```


### алиасы для bash
```bash
vim ~/.bashrc
alias djmigrate='python manage.py migrate'
alias djmakemigrations='python manage.py makemigrations'
alias djtest='python manage.py test'
source ~/.bashrc
```

