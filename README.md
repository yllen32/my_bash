# my_bash
Полезные скрипты


Зайти в каждую папку, прочесть все файлы info и перенаправить вывод в один файл.

```sh
 for dir in *; do (cd "$dir" && cat info.txt >> /f/m/total.txt && printf "\n-----" >> /f/m/total.txt); done
 ```
