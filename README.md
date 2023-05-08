# GIT
Привет! Здесь о том, как я изучала команды GIT и работала в bash в рамках интенсива от "Школы седого тестировщика" и курса "Тестировщик с нуля" Артёма Русова.
Это портфолио собрано из моих домашних заданий)

## Оглавление
1. [Основные команды.](#основные-команды)
2. [Ветки. Создание, удаление, слияние.](#ветки-создание-удаление-слияние)
3. [Отмена изменений. Git Reset.](#отмена-изменений-git-reset)

_____

### Основные команды.

```git status```
>Показывает текущую ситуацию в репозитории
>
>![image](https://user-images.githubusercontent.com/97261554/236861851-69d3bfcb-2f56-4f00-bc25-502fe37d2998.png)

```git commit```
>

```git commit -am "file3.txt"```
>Добавление файла без индексации, то есть пропуская этот этап, он автоматич проиндексируется. Это работает только с теми файлами, которые уже были проиндексированы когда-то. С новыми - нет.
>
>![image](https://user-images.githubusercontent.com/97261554/236724873-05122144-42fc-4c89-9199-73c04748923f.png)

```git commit -m “add second.txt” second.txt```
>Комит определённого файла. В данном случае second.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236727689-c1162665-a5d8-42c6-b33f-494a8411603d.png)

```git add```

```git add .```

```git add “название файла”```

```git add -A```
>Проиндексировала изменения во всех директориях, находясь при этом в папке folder2
>
>![image](https://user-images.githubusercontent.com/97261554/236725542-c57725b5-7956-4c9b-a95a-fd9eca68a4aa.png)

```git rm -r --cached first.txt```
>Удалила файл first.txt из индексации
>
>![image](https://user-images.githubusercontent.com/97261554/236725818-c33e2b25-ca00-46f7-8a0b-26461a2965d1.png)

```git rm -r first.txt```
>Удалила файл first.txt из репозитория и проиндексировала это изменение
>
>![image](https://user-images.githubusercontent.com/97261554/236725993-4b1cc02a-50d4-4f25-98bb-53fcd8ba3766.png)

```git rm -f folder4file1.txt```
>Удалила непроиндексированный файл folder4file1.txt
>Функция -f - игнорирует все предупреждение гита
>
>![image](https://user-images.githubusercontent.com/97261554/236726072-27af8003-d4f4-46e4-8d77-5fc2d2ffe4b3.png)

```git mv second.txt third.txt```
>Переименовала и проиндексировала файл second.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236726252-9e47e6f6-5af4-445e-90ad-0270e44f7b44.png)

```git log```
>История комитов с автором и датой
>
>![image](https://user-images.githubusercontent.com/97261554/236727866-b9610409-c4a4-403a-a498-4c3ef22d6027.png)

```git log -p```
>Более подробная история комитов. Показаны добавленные и удалённые строки в файлах.
>
>![image](https://user-images.githubusercontent.com/97261554/236727935-e02961b1-9e5b-4cbc-89b3-130dd5d6a524.png)

```ls -la```
>Показывает список всех файлов, в т.ч. скрытых системных
>
>![image](https://user-images.githubusercontent.com/97261554/236861481-fc0c9db8-b863-4830-a759-4faec7a54cfa.png)


```git show```
>Информация по последнему комиту.
>
>![image](https://user-images.githubusercontent.com/97261554/236726584-ea63f67b-e74e-4b20-af07-d449c1047f04.png)

```git diff```
>Показывает непроиндексированные изменения в проиндексированных файлах. В данном случае, у меня было 2 подготовленных к комиту файла. Я решила внести изменения в файл dog.txt. Команда git diff показала мне эти изменения.
>
>![image](https://user-images.githubusercontent.com/97261554/236728045-5e347322-6b69-4cc1-a3bd-5048dacac42f.png)

```git diff —staged```
>Я закомитила первоначальную версию файлов cat.txt и dog.txt. После этого подготовила к комиту новую версию файла dog.txt. И сравнила 2 версии файла dog.txt командой git diff --staged (первая - уже сохранённая, а вторая только подготовлена).
>
>![image](https://user-images.githubusercontent.com/97261554/236726839-34dc577a-5887-41f4-bd78-8a0baa89076d.png)

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
>![image](https://user-images.githubusercontent.com/97261554/236730785-c2425f31-4190-4937-8f0f-bd7486ac42d4.png)

```git show a505bdf```
>Посмотреть определённый комит по его номеру
>
>![image](https://user-images.githubusercontent.com/97261554/236730533-dd5db702-4398-4169-b64f-c0085e0e6be0.png)

_____

### Отмена изменений. Git Reset.

```git reset --hard 153a36```
>Откатила изменения до комита 153a36
>
>![image](https://user-images.githubusercontent.com/97261554/236731217-cdd1760b-081c-4963-b539-af5174bb2833.png)

```git reset —hard ORIG_HEAD```
>Отменила предыдущий откат
>
>![image](https://user-images.githubusercontent.com/97261554/236731288-c7aa2587-5235-42c1-a49f-012dcfd877dd.png)

```git reset —hard```
>Перешла к состоянию последнего выполненного комита,отменила все незакомиченные изменения
>
>![image](https://user-images.githubusercontent.com/97261554/236731353-9d9ba506-689d-4061-a8f3-81135b4aa671.png)

```git reset --soft 359b841```
>Откатилась до комита 359b841, сохранив в индексе все изменения, сделанные после этого комита
>
>![image](https://user-images.githubusercontent.com/97261554/236731463-2d2d289b-9cc5-4b0e-9ebf-d137d04188e1.png)

```git commit —amend```
>Исправила комментарий предыдущего комита
>
>![image](https://user-images.githubusercontent.com/97261554/236731568-568a3ba9-001d-4e95-989d-d00cbbbb46c2.png)

```git log —oneline```
>Вывела кратую инфу по логу
>
>![image](https://user-images.githubusercontent.com/97261554/236731658-7439d113-b7ac-44ff-b817-4146c3d46abe.png)

```git log main --oneline```
>Вывела краткий лог определённой ветки
>
>![image](https://user-images.githubusercontent.com/97261554/236731765-de7de149-7e18-4fc7-884a-7e0d31fd085d.png)

```git show a505bdf dog.txt```
>Посмотрела содержание файла dog.txt в комите a505bdf
>
>![image](https://user-images.githubusercontent.com/97261554/236731951-da5667ea-dc87-4a54-bb09-46fe860f2aa0.png)

```git show :check2.txt```
>Посмотрела проиндексированные изменения в файле check2.txt
>
>![image](https://user-images.githubusercontent.com/97261554/236732108-1565a628-c837-43b2-8743-b124945a5aa2.png)

```git log --grep "save"```
>Нашла комит, содержащий в комментарии ключевое слово "save"
>
>![image](https://user-images.githubusercontent.com/97261554/236732200-8d71cef2-d9f3-4243-b9e8-a018d6e6456f.png)
