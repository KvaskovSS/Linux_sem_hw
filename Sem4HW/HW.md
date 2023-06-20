# Homework

## Вывести на экран 3 раза имя пользователя, от которого запускается команда:
```
#!/bin/bash

user=$(whoami)

for ((i=0; i<3; i++)); do
    echo $user
done
```

## Вывести с помощью цикла while все четные числа от 0 до 100 включительно:

```
#!/bin/bash

num=0

while [[ $num -le 100 ]]; do
    echo $num
    ((num += 2))
done
```

## Использовать команду 'cut' для вывода прав доступа файлов текущей папки, сортировки и удаления дубликатов:
```
#!/bin/bash

ls -l | cut -d ' ' -f 1 | sort | uniq
```
## Скрипт очистки директорий:

#!/bin/bash

directory=$1

if [ -d "$directory" ]; then
    find "$directory" -type f \( -name "*.bak" -o -name "*.tmp" -o -name "*.backup" \) -delete
else
    echo "Директория не существует."
fi
