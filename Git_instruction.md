![logo](Git-Logo-1788C.png)
# Работа c Git и GitHub

## 1. Проверка наличия установленного Git
В терминале выполнить команду  `git --version`. Если Git установлен, появится сообщение  с информацией о версии программы, иначе будет сообщение об ошибке.

## 2. Установка Git
Загружаем последнюю версию Git c  сайта https://git-scm.com/downloads. устанавливаем с настройками по умолчанию

## 3. Настройка Git
При первом использование Git необходимо представится. Для этого необходимо выполнить в терминале 2 команды

```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Инициализация локального репозитория
Для этого необходимо выбрать(создать) папку в проводнике. В терминале выполнить команду `git init`
## 5 . Проверка статуса о текущем состояние
Выполняем команду `git status` в терминале появится надпись 
```$ git status
On branch master
nothing to commit, working tree clean
```
## 6. Добавление файла
Для этого необходимо в проводнике (вкладка файл) создать (выбрать) файл, а в терминале выполнить команду `git add "name file"` . И при проверке статуса будет:
```
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   "name file"
```
## 7. Добавление коммита
В терминале выполняем команду `git commit -m "text commit"` в терминале будет:
```
$ git commit -m "text commit"
[master da0f696] text commit
 1 file changed, 12 insertions(+), 2 deletions(-)
 ```
 * для того чтобы увидить историю коммитов необходимо выполнить команду `git log  или git log --oneline`
 * `git checkout` – переход от одного коммита к другому. например: git checkout 4198819c(это хеш тег коммита)

 * `git checkout master` – вернуться к актуальному состоянию и продолжить работу
* `git diff` – увидеть разницу между текущим файлом и закоммиченным файлом


## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл  **.gitignore** и записать в него их названия или шаблоны (*.расширение файла), соответствующие таким файлам или папкам

## 9. Добавление веток в Git
По умолчанию имя  ветки **master**. Для того чтобы создать новую ветку необходимо выполнить команду:
```
git branch <имя новой ветки>
или
git checkout -b <name branch> - создание и перемещение в новую ветку
```

Список Веток в репозитории можно посмотреть с помощью команды


```
git branch 

```

Текущая ветка ,будет отмечена **\*master.**

Для перемещения между ветками используем команду 
```
git checkout "name branch"
или
```
## 10. Удаление веток в Git
Для того чтобы, удалить ветку не обходимо выполнить команду
```
git branch -d <name branch>
или
git branch --delete <name branch>
```
Примечание: удалить ветку можно только тогда когда ты не находишся в ней.

Если ветка не слита с необходимой веткой при удаление появится предупреждение 
```$ git branch -d name branch
error: The branch 'name branch' is not fully merged.
If you are sure you want to delete it, run 'git branch -D name branch'.
```
Где команда ***git branch -D name branch*** принудительно удалит ветку. ***ВНИМАНИЕ все неслитые данные будут удалены*** 

## 11. Сливание веток
Для того чтобы слить ветку необходимо выполнить команду : 
```
git merge "название ветки"
```
 и закомитить сливание.
 Сливание веток может произайти с конфликтом если в одной из веток на тех же строках что и в ветке **master** находится информация  то необходимо решить конфликт в ручную выбрать один из предложенных вариантов.
 
 
 ## Работа с GitHub
 1. Создаём аккаунт на GitHub __https://github.com/__

 2. Создать удаленный репозиторий в своем аккаунте на GitHub. 
 
 3. Создать локальный репозиторий.
 
 4. Выполнить быструю настройку (*подружить локальный и удаленный репозиторий*)
  выбрав 2-й предложенный вариант настройки в браузере и выполнить эти команды в терминале (пример):
  ```
  git remote add origin https://github.com/KirichenkoAlexandr/name.git
  git branch -M main
   git push -u origin main
 ```
  если все выполнено правильно при обновление браузера у вас появится Ваш репозиторий.

 5. Для того чтобы отправить изменения локального репозитория в удаленный необходимо выполнить команду **git push**. После в терминале появится:
 
 ```
 $ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 298 bytes | 298.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/KirichenkoAlexandr/name.git
   f8aa36d..5fb0bbb  main -> main
   ```
   что будет обозначать удачную отправку в удаленный репозиторий.
   
   6. При необходимости в браузере есть встроенный редактор в котором можно редактировать информацию вашего проэкта для этого необходимо зайти в необходимый файл и выбрать в праволм верхнем углу иконку `edit this file` ![icon](1234.jpeg), и так же после редактирования файлла оставить *commit* при помощи иконки ![icon](123.jpeg)
   
   7. Для того чтобы эти изменения появилися в вашем локальном репозитории необходимо выполнить команду в терминале *git pull*
   после чего в терминале появится 
   ```
   $ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 713 bytes | 237.00 KiB/s, done.
From https://github.com/KirichenkoAlexandr/name
   5fb0bbb..712a1a1  main       -> origin/main
Updating 5fb0bbb..712a1a1
Fast-forward
 START.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
 ```
 что обозначает удачное скачивание репозитория.
 
 ***Примечание***: конфилты решаются также как и ранее.
 
## Работа с чужим удаленным репозиторием (Pull requests)
1. для того чтобы начать работу с чужим удаленным репозиторием его необходимо найти в строке поиска либо перейти по предоставлнной вам ссылке. После необходимо его копировать при помощи кнопки *Fork* После чего он появится в вашем профиле.
2. Нажать кнопку  *Code* ![icon](12345.jpeg) после чего выбрать ссылку скопировать ее и клонировать репозиторий на локальный компьютер
при помощи команды *git clone url-adress* например :*git clone  https://github.com/AndreyBulgakov19/SCV_Git_PR.git*
 после чего в терминале произойдет загрузка. И в проводнике появится копия чужого репозитория.
 3. Дя того чтобы начать работать в этом репозитории необходимо в него перейти при помощи команды *cd name repository*  ##ОБЯЗАТЕЛЬНО## необходимо создать новую ветку и перейти в нее. Далее можно вносить изменения, и добавлять коммиты.

 4. После того как внесли изменения  отправляем в удаленный репозиторий при помощи команды *git push*. В случае если нет такой ветки в этом репозитории появится надпись
 ```
 git push
fatal: The current branch new1 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin new1

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.
```
тогда выполняем команду которую нам предлогает Git: *git push --set-upstream origin (имя ветки которую Вы создали)*
после чего в терминале появится надпись 
```
$ git push --set-upstream origin new1
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 283 bytes | 283.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'new1' on GitHub by visiting:
remote:      https://github.com/KirichenkoAlexandr/SCV_Git_PR/pull/new/new1
remote:
To https://github.com/KirichenkoAlexandr/SCV_Git_PR.git
 * [new branch]      new1 -> new1
branch 'new1' set up to track 'origin/new1'.
```
что обозначает удачную загрузку. После этого в вашем профиле в этом репозитории появятся ваши изменения, если их не видно то не обходимо в кнопке ![icon](123456.jpeg) выбрать новую ветку и увидить все свои изменения. и жмем кнопку ![icon](1234567.jpeg) . после чего переходит на следующюю страницу и там жмем ![icon](12345678.jpeg). Вуаля pull request выполнен. Автор проекта увидит ваши дополнения (изменения).



