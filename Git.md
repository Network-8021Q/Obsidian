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


