# my_bash
Полезные скрипты


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
