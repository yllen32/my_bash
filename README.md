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

 ### SSH тунелирование
```ssh
ssh -L 9998:localhost:15672 -p 2223 user@server -N # можно еще -f для запуска в бэкграунде
# L проброс портов
# N не открывать терминал на машине
```
### vim

простая замена

:%s/текс который нужно заменить/ текст на который меняем/g(можно добавить .с. тогда будет просить подтверждение)

```sh
# пройтись по всем файлами и подфайлам текущей директории и изменить текст в файлах *.py
vim -c "bufdo! set eventignore-=Syntax | :%s/текс который нужно заменить/ текст на который меняем/gce" **/*.py# e для игнорирования ошибок
# убедись что ввел перед этим
shopt -s globstart
```

```sh
cat .env | grep -E 'FLOWER_|REDIS_' > .filtered.env
```

Удаление всех файлов миграций
```sh
find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
```

#Запуск видео сервера
```sh
docker pull prologic/tube
docker run -p 8000:8000 -v ~/data:/data prologic/tube
# для конвертирования видео mkv
sudo apt install ffmpeg
ffmpeg -i ~/Django.mkv -c:v copy -c:a aac -sn ~/data/videos/django.mp4

```
