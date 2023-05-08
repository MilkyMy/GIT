# GIT
Привет! Здесь о том, как я изучала команды GIT и работала в bash в рамках интенсива от "Школы седого тестировщика" и курса "Тестировщик с нуля" Артёма Русова.
Это портфолио собрано из моих домашних заданий)

## Оглавление
1. [Конфигурация GIT. Создание и клонирование репозитория.](#конфигурация-git-создание-и-клонирование-репозитория)
2. [Коммиты и работа с файлами.](#коммиты-и-работа-с-файлами)
3. [Ветки. Создание, удаление, слияние.](#ветки-создание-удаление-слияние)
4. [Отмена изменений. Git Reset.](#отмена-изменений-git-reset)
5. [Изучение инструмента SmartGit.](#изучение-инструмента-smartgit)
_____

### Конфигурация GIT. Создание и клонирование репозитория.
1. Создать удаленный репозиторий.
2. Добавить один файл и папку с двумя файлмаи
3. Добавить файл гитигнор и добавить в него любой файл.
4. Ссылку на репозиторий необходимо скинуть преподавателю. Также необходимо скинуть файл с настройками пользователя + скриншот информации о пользователе в самом гите. Вывести можно через list —global

_____

### Коммиты и работа с файлами.

```Git commit -am```
>Индексация и комит уже подготовленного к комиту, но изменённого файла file3.txt.
>
>![image](https://user-images.githubusercontent.com/97261554/236724873-05122144-42fc-4c89-9199-73c04748923f.png)

```Git commit -m “add second.txt” second.txt```
>Комит определённого файла. В данном случае second.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236727689-c1162665-a5d8-42c6-b33f-494a8411603d.png)

```Git add -A```
>Проиндексировала изменения во всех директориях, находясь при этом в папке folder2
>
>![image](https://user-images.githubusercontent.com/97261554/236725542-c57725b5-7956-4c9b-a95a-fd9eca68a4aa.png)

```Git rm -r --cached first.txt```
>Удалила файл first.txt из индексации
>
>![image](https://user-images.githubusercontent.com/97261554/236725818-c33e2b25-ca00-46f7-8a0b-26461a2965d1.png)

```Git rm -r first.txt```
>Удалила файл first.txt из репозитория и проиндексировала это изменение
>
>![image](https://user-images.githubusercontent.com/97261554/236725993-4b1cc02a-50d4-4f25-98bb-53fcd8ba3766.png)

```Git rm -f folder4file1.txt```
>Удалила непроиндексированный файл folder4file1.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236726072-27af8003-d4f4-46e4-8d77-5fc2d2ffe4b3.png)

```Git mv second.txt third.txt```
>Переименовала и проиндексировала файл second.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236726252-9e47e6f6-5af4-445e-90ad-0270e44f7b44.png)

```Git log```
>История комитов с автором и датой
>
>![image](https://user-images.githubusercontent.com/97261554/236727866-b9610409-c4a4-403a-a498-4c3ef22d6027.png)

```Git log -p```
>Более подробная история комитов. Показаны добавленные и удалённые строки в файлах.
>
>![image](https://user-images.githubusercontent.com/97261554/236727935-e02961b1-9e5b-4cbc-89b3-130dd5d6a524.png)

```Git show```
>Информация по последнему комиту.
>
>![image](https://user-images.githubusercontent.com/97261554/236726584-ea63f67b-e74e-4b20-af07-d449c1047f04.png)

```Git diff```
>Показывает непроиндексированные изменения в проиндексированных файлах. В данном случае, у меня было 2 подготовленных к комиту файла. Я решила внести изменения в файл dog.txt. Команда git diff показала мне эти изменения.
>
>![image](https://user-images.githubusercontent.com/97261554/236728045-5e347322-6b69-4cc1-a3bd-5048dacac42f.png)

```Git diff —staged```
>Я закомитила первоначальную версию файлов cat.txt и dog.txt. После этого подготовила к комиту новую версию файла dog.txt. И сравнила 2 версии файла dog.txt командой git diff --staged (первая - уже сохранённая, а вторая только подготовлена).
>
>![image](https://user-images.githubusercontent.com/97261554/236726839-34dc577a-5887-41f4-bd78-8a0baa89076d.png)

_____

### Ветки. Создание, удаление, слияние.

```git branch```
>Показывает в какой ветке я нахожусь
>
>![image](https://user-images.githubusercontent.com/97261554/236728450-599deb05-a4ee-46db-9975-211f86538aee.png)

```git branch -v```
>Более детальная инф-я о ветке, показывает последний коммит
>
>![image](https://user-images.githubusercontent.com/97261554/236728596-f8521f3f-3d05-4fa2-b426-b225c1eaf127.png)

```git branch v1```
>Создала новую ветку - v1
>
>![image](https://user-images.githubusercontent.com/97261554/236728716-7a50358a-b2ac-45de-a5ee-51e17cb898c8.png)


```git checkout v1```
>Переключилась на ветку v1
>
>![image](https://user-images.githubusercontent.com/97261554/236729532-e02f1a53-3cfa-4eab-989a-98f819bde869.png)

```git checkout -f main```
>Переключилась на ветку main без сохранения изменений в ветке v1
>
>![image](https://user-images.githubusercontent.com/97261554/236729597-6c2c93df-376e-45f1-93ba-cc4133a0e3ac.png)

```git checkout -f```
>Удалила все незакомиченные изменения
>
>![image](https://user-images.githubusercontent.com/97261554/236729685-a70f2102-0fbc-4dcf-9499-45796e9e15db.png)

```git stash```
>Сохранила все незакомиченные изменения и откатилась до предыдущего комита
>
>![image](https://user-images.githubusercontent.com/97261554/236729832-1301dd25-6e90-47de-8ed1-701e712de70f.png)

```git stash pop```
>Вернулась к этим изменениям
>
>![image](https://user-images.githubusercontent.com/97261554/236729967-628ef8ac-62da-4aa0-89bd-bf8ac68d4980.png)

```git checkout bird.txt```
>Откатила изменения до последней проиндексированной версии
>
>![image](https://user-images.githubusercontent.com/97261554/236730094-b7fd9cdb-5ba6-48ec-b737-721b235317ab.png)

```git merge v1```
>Произвела слияние ветки v1 с главной веткой main
>
>![image](https://user-images.githubusercontent.com/97261554/236730201-525c5fd1-cc26-46b1-ab50-2d267308924f.png)

```git branch -d v1```
>Удалила ветку v1
>
>![image](https://user-images.githubusercontent.com/97261554/236730298-ba45ed8d-4cec-4647-b7d4-ddddb7949837.png)

```git branch -D v2```
>Удалила несмерженную ветку v2
>
>![image](https://user-images.githubusercontent.com/97261554/236730415-e29259b7-bf7a-495d-9464-175bea1f430a.png)

```git show a505bdf```
>Посмотреть определённый комит по его номеру
>
>![image](https://user-images.githubusercontent.com/97261554/236730533-dd5db702-4398-4169-b64f-c0085e0e6be0.png)

_____

### Отмена изменений. Git Reset.

```git reset —hard номер_коммита```

```git reset —hard ORIG_HEAD```

```git reset —hard```

```git reset —soft номер_коммита```

```git commit —amend```

```git log —oneline```

```git log название ветки —oneline```

```git show коммит:название файла```

```git show :название файла```

2. Найти опцию и выполнить команду показа всех коммитов по определенному ключевому слову из комментария.
https://git-scm.com/book/ru/v2

_____

### Изучение инструмента SmartGit (изменит название).

```git add -p```
>Проиндексировала часть изменений в файле
>
>![image](https://user-images.githubusercontent.com/97261554/236727025-a809dd46-c8cc-400c-ada4-af9d89cb7243.png)
>![image](https://user-images.githubusercontent.com/97261554/236727362-12e476b6-ad8e-4301-b751-10f3e03366a1.png)

```git pull```
>Подтянула изменения из удалённого репозитория в локальный c созданием дополнительной ветки и комита
>
>![image](https://user-images.githubusercontent.com/97261554/236727449-c6744cc1-143e-4a3b-939c-047de8b7d70a.png)

```git pull --rebase```
>Подтянула изменения из удалённого репозитория в локальный без создания дополнительной ветки и комита
>
>![image](https://user-images.githubusercontent.com/97261554/236727536-58e05e29-3af1-4465-962a-3d66f08504a7.png)


2. Использовать SmartGit для:
- Подключения локального репозитория
- Индексации файлов
- Коммита изменений
- Изменения последнего коммита
- Создания веток
- Слияния веток
- Клонирования удаленного репозитория
- Обновления удаленного репозитория (merge и rebase)
- Отправки изменений в удаленный репозиторий
