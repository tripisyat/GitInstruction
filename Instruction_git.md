# Инструкция по работе с GIT

## Что такое git
Это система для конироля версионности.
[Wiki ссылка](https://ru.wikipedia.org/wiki/Git)

## Подготовка репозитория
Для инициализации репозитория выполнить
```sh
git init
```
## Создание и сохранение
Посмотреть статус репозитория 
```sh
git status
```
Добавить измененный файл к интексации
```sh
git add filename.md
```
Зафиксировать изменения 
```sh
git commit -m "Message for commit"
```
## Перемещение между сохранениями
Для перемещения между сохранениями (commit) набрать
```sh
git checkout хэш коммита
```
Для перемещения между ветками набрать
```sh
git checkout branch_name
```
## Журнал изменений
Вывести все сохранения (commit) на экран
```sh
git log
```
Вывести все сохранения (commit) на экран в сокращенном виде
```sh
git log --oneline
```
Вывести все сохранения (commit) на экран в сокращенном виде с графическим изображением веток
```sh
git log --oneline --graph
```
## Ветки в git
Создать новую ветку
```sh
git branch branch_name
```
Вывести список всех имеющихся веток
```sh
git branch
```
Перейти на нужную ветку
```sh
git checkout branch_name
```
Создать ветку и сразу на неё перейти
```sh
git checkout -b branch_name
```
### Слияние веток
Для слияния веток обе ветки должны быть закоммичены! Необходимо перейти в ветку в которую будешь вливать и из неё выполнить
```sh
git merge branch_name_for_merge
```
Если вдруг какая то ветка не закомичена, можно при сливании сразу закоммитеть
```sh
git merge branch_name_for_merge -m "Message for commit"
```
### Удаление веток
Для удаления ветки выполнить
```sh
git branch -d branch_name
```
# Работа с GitHub

**Git** - программа (терминал) на компьютере

**GitHub** - удаленный сервис, который позволяет хранить репозитории в облаке
1. Создаем аккаунт на GitHub
2. Можно авторизоваться в VS code, используя логин и пароль GitHub

## Как стянуть/скачать удаленный репозиторий на компьютер?
В терминале набрать 
```sh
git clone ссылка на репозиторий (URL)
```
в папке появится новая папка с названием скаченного репозитория
для перехода в ней выполнить 
```sh
cd имя папки
```
можно приступать к работе

Если нужно скачать обновленную версию этого репозитория с GitHub выполнить
```sh
git pull
```
при этом скачается актуальная версия репозитория и выполнится слияние локального и удаленного репозитория

## Как отправить репозиторий в GitHub после правок?
после последнего коммита выполнить
```sh
git push
```
## Как отправить локальный репозиторий в GitHub которого ещё там не существует?
Создать пустой репозиторий в GitHub

Скопировать ссылку на этот репозиторий

В терминале в папке локального репозитория выполнить
```sh
git remote add origin ссылка на репозиторий
```
```sh
git branch -M main
```
```sh
git push -u origin main
```

## Как предложить свои правки кому то? Делаем Pull request
1. В интересующем нас репозитории нажимаем кнопку **Fork**. При этом мы делаем полную копию данного репозитория к себе в аккаунт.

2. На компе выполняем 
```sh
git clone ссылка на этот репозиторий
```
3. После скачивания репо, переходим в папку этого репо
```sh
cd имя папки
```
4. Делаем новую ветку 
```sh
git branch имя ветки
```
5. Переходим на эту ветку и работаем только в ней
```sh
git checkout имя ветки
```
6. После правок коммитем 
```sh
git add имя файла
git commit -m "Комментарий"
```
7. Отравляем изменения в свой аккаунт
```sh
git push
```
8. Перейти в данный репозиторий в своем аккаунте сверху закладка *Pull request*. Нажать на кнопку Pull request

## Заметки
Для того чтобы очиcтить терминал набирите
```sh
clear
```
Чтобы git не ругался на незакомиченные файлы (например, фото, которые не принято добавлять в git), то создается в проекте файл
```sh
.gitignore
```
и записываем в него названия этих файлов с расширением.
Затем этот файл (.gitignore) добавляем в git 
```sh
git add .gitignore
```
и делаем ему commit, например
```sh
git commit -m "добавили .gitignore"
```
