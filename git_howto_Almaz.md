# Подсказки по Git

## Создание репозитория

```sh
git init
```

## Добавить изменения в файл

```sh
git add "название файла"
```

## Добавить коммент, что мы конкретно сделали с файлом

```sh
git commit -m "Осмысленное описание совершенных действий"
```

## Загрузить точку сохранения

```sh
git checkout "Первые 6 цифр точки сохранения" или имя ветки
```

## Картинка

![Инь-Янь](inei.JPG "всплывающий текст при наведении")

## Показать различия между точками сохранения

```sh
git diff
```

Зачеркнутый text ~~Very much bad words~~

## Добавление ссылки

[ШБ №1](http://www.puncherschool.ru/ "бокс детишкам")

## Отображение всех веток

```sh
git branch
```

## Выход из редактора Wim

```sh
Нажать Esc, затем :wq и всё
```

## Слияние веток

```sh
Перейти в основную ветку и набрать команду 
git merge "название ветки"
```

## Откатить Git до определенного хэша

```sh
git reset --hard и "хэш или тэг коммита, до которого нужно удалить коммиты, после чего данный хэш станет последним коммитом"
```

## Learn git Branching

## Делай ветки сразу, делай ветки часто

1. Команда clear - очистить терминал
2. Показать существующие ветки проекта - git branch
3. Удаление ветки - git branch -d "branch name"
4. Создать ветку - git branch "branch name"
5. Создать ветку и сразу же на неё переключиться - git branch -b "branch name"
6. Вывести все хэши в одну строку - git log --oneline
7. Вывести все хэши в одну строку графически - git log --oneline --graph

**Git log всегда вызывается с последнего коммита текущей (выбранной) ветки HEAD**

8. Слияние веток - git merge (*делается из ветки, в которую нужно влить лругую ветку)
9. Слияние веток - git rebase "название ветки, в которую нужно влить изменения" (*делается из ветки, которую нужно переместить)

## HEAD - тот коммит, над которым мы в данный момент работаем

1. Перемещение по ветке на предыдущий хэш - git checkout "name branch"^ либо git checkout "name branch"~<количество отматываемых комитов>

    **Номер после ^ определяет, на какого из родителей мерджа надо перейти. Учитывая, что мерджевый коммит имеет двух родителей, просто указать ^ нельзя, иначе Git по умолчанию перейдёт на "первого" родителя коммита, но указание номера, например 2 после ^ изменяет это поведение.**

2. Перемещение ветки "branch forcing" - git branch -f "название ветки, которую нужно переместить, относительно *текущей ветки HEAD" и*текущая ветка HEAD~(указать количество отматываемых комитов)
3. Отменить изменения в локальном репо - git reset "branch name" (откатит изменения на комит назад)
4. Отменить изменения и поделиться отменёнными изменениями в удаленном репо - git revert "branch name"
5. Копирование одного или нескольких коммитов на место, где сейчас находишься* (HEAD) - git cherry-pick <Commit1> <Commit2> и так далее.
6. Перемещение/удаление комитов из ветки - git rebase -i HEAD~(указать количество редактируемых комитов, включая текущий)
7. Внесьти изменения в комит - git commait --amend

## Tags - метки

1. Создать тэг - git tag "задать название тэга" "указать хэш комита, к которому добавляем тэг"
2. Команда, которая показывает, как далеко текущее состояние от ближайшего тега - git describe "что-либо, уазывающее на конкретный комит" либо HEAD

**Вывод команды выглядит примерно так:**

        <tag>_<numCommits>_g<hash>

**Где tag – это ближайший тег в истории изменений, numCommits – это на сколько далеко мы от этого тега, а hash – это хеш коммита, который описывается.**

## **Работа с удалёнными репозиториями** HOMEWORK 3

**GitHub** - один из сервисов для работы с удалёенными репозиториями

1. Подключение удаленного репозитория - git clone "ссылка из Github под кнопкой CODE"

2. Изменить директиву переключившись в склонированную папку - cd "название папки с .git"

3. Связать локальный репозиторий с удаленным - git remote add origin "ссылка на Github"

4. Отправить изменения из локального в удаленный репозиторий - git push или git push -u origin main

5. Отправить изменения из удаленного в локальный репозиторий - git pull(сразу делает merge) или git fetch(без merge)

6. После push на свой акк в Github, необходимо сделать запрос на merge владельцу репозитория - Pull request

**Fork** - процесс копирования чужого репозитория на свой аккаунт.