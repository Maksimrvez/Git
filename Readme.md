# Первоначальная настройка Git
> **Первое, что вам следует сделать после установки Git— указать ваше имя и адрес электронной почты.**
  
~~~
git config --global user.name ""
git config --global user.email ""
~~~

- [X] Создать локально новый репозиторий

~~~
git init
~~~

## Просмотр конфигураций удаленных репозиториев
- [X] Список ваших удаленных подключений к другим репозиториям.

~~~
git remote
~~~

> **Аналогично команде выше, но включает URL-адрес каждого подключения.**

~~~
git remote -v
git remote add <name> <url>
~~~

- [X] Удаление подключения к удаленному репозиторию с именем.

~~~
git remote rm <name>
~~~

## Работа с удалёнными репозиториями

- [X] Клонировать существующий репозиторий

~~~
git clone <url>
~~~

## Загрузка репозитория на сайт/локальный сервер**
> **Локальный**

- [X] Добавить все измененные файлы в индекс репозитория.

~~~
git add .
~~~

- [X] Запись индексированных изменений в репозиторий Git.

~~~
git commit -m "Первый коммит"
~~~

- [X] Переимновать индексированные изменения

~~~
git commit --amend -m "Новый коммит"
~~~

## Сайт
- [X] Отправка изменений**

~~~
git push -u origin main
~~~

- [X] Извлечь из указанного удаленного репозитория копию текущей ветки и немедленно слить ее с локальной копией.

~~~
git pull
~~~

## Работа с ветками в Git
> **Команда git branch — главный инструмент для работы с ветвлением. С ее помощью можно добавлять новые ветки, перечислять и      переименовывать существующие и удалять их.**

- [X] Список всех существующих веток**

~~~
git branch -av
~~~

- [X] Переключение в ветки**

~~~
git checkout <ветка>
~~~

- [X] Создать новую ветку**

~~~
git branch <новая-ветка>
~~~

- [X] Создать новую ветку и сразу переключится в нее**

~~~
git checkout -b <новая-ветка>
~~~

- [X] Удалить локальную ветку

~~~
git branch -d <ветка>
~~~

- [X] Локальные изменения
> **Файлы в рабочей директории были изменены**

~~~
git status
~~~

- [X] Изменения в отслеживаемых файлах

~~~
git diff
~~~

~~~
git diff <commit1> <commit2>
~~~

## История коммитов
- [X] Показать всю историю коммитов начиная с последних

~~~
git log
~~~

- [X] Показать историю изменений определенного файла

~~~
git log -p <файл>
~~~

- [X] Кто, какие и когда изменения вносил в <файл>

~~~
git blame <файл>
~~~

## Отмена
> **Удалить все локальные изменения в рабочем каталоге**

***Это самый прямой, ОПАСНЫЙ и часто используемый вариант. При использовании аргумента --hard указатели в истории коммитов обновляются на указанный коммит. Затем происходит сброс раздела проиндексированных файлов и рабочего каталога до указанного коммита. Все предыдущие ожидающие изменения в разделе проиндексированных файлов и рабочем каталоге сбрасываются в соответствии с состоянием дерева коммитов. Это значит, что любая работа, находившаяся в состоянии ожидания в разделе проиндексированных файлов и рабочем каталоге, будет потеряна.***
  
~~~
git reset --hard <хэшcommit>
~~~

> ***Это режим работы по умолчанию. Указатели ссылок обновляются. Раздел проиндексированных файлов сбрасывается до состояния указанного коммита. Любые изменения, которые были отменены в разделе проиндексированных файлов, перемещаются в рабочий каталог.***

~~~
git reset --mixed <хэшcommit>
~~~

> ***При передаче аргумента --soft выполняется обновление указателей, и на этом операция сброса останавливается. Раздел проиндексированных файлов и рабочий каталог остаются неизменными. Четко продемонстрировать такое поведение довольно сложно.***

~~~
git reset --soft <хэшcommit>
~~~

> ***Сбрасывает раздел проиндексированных файлов и рабочий каталог до состояния последнего коммита. Флаг --hard говорит Git, что нужно не только отменить изменения в разделе проиндексированных файлов, но и перезаписать все изменения в рабочем каталоге. Другими словами, эта команда уничтожит все неотправленные изменения, поэтому перед ее использованием убедитесь, что вы действительно хотите удалить ваши локальные наработки.***

~~~
git reset --hard
~~~

- [X] Вернуть файл из стейджинга, но оставить изменения в нем неприкосновенными.

~~~
git restore --staged myFile.txt
~~~

- [X] Отменить локальные изменения в конкретном файле

~~~
git restore myFile.txt
~~~