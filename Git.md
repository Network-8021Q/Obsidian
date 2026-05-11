```
# Оставить свои версии обоих конфликтующих файлов
git checkout --ours .obsidian/workspace.json
git checkout --ours "Network (IS).md"

# Отметить как решённые
git add .obsidian/workspace.json
git add "Network (IS).md"

# Удалить применённый stash
git stash drop

# Готово!
git status
```


Ошибка: Если были локальные изменения в файле .obsidian/workspace.json которые конфликтуют с изменениями из удалённого репозитория

Решение:

```bush
# Спрятать локальные изменения
git stash

# Выполнить pull
git pull origin master

# Вернуть локальные изменения обратно
git stash pop
```