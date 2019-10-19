# Как сделать pull request

Перед тем как сделать свой первый пулл, мы рекомендуем пройти курс по основам Git на [GitHowTo](http://githowto.com/ru/setup).

- [Регистрация на GitHub](pull.md#Регистрация-на-github)
- [Как сделать pull request прямо на GitHub](pull.md#Как-сделать-pull-request-прямо-на-github)
- [Как сделать pull request в windows](pull.md#Как-сделать-pull-request-в-windows)
- [Как сделать pull request в linux](pull.md#Как-сделать-pull-request-в-linux)
- [Как закешировать пароль](https://help.github.com/articles/caching-your-github-password-in-git/)

## Регистрация на GitHub

Если у вас нет аккаунта на Github – регистрируемся по ссылке http://github.com/join  
<img width="780" alt="github-signup" src="https://cloud.githubusercontent.com/assets/4534405/19143150/5dffcfbc-8bbb-11e6-8ab7-747dfbe433fa.png">

Если есть – просто входим по ссылке http://github.com/login  
<img width="333" alt="github-login" src="https://cloud.githubusercontent.com/assets/4534405/19143216/c96e668c-8bbb-11e6-96b6-583957a31b16.png">

## Пришглашение в репозиторий задачи

Задачи выполняются в приватных репозиториях, поэтому в начале каждой задачи, вам придет приглашение в ваш **личный** репозиторий с этой задачей.

Приглашение придет вам на почту. Так же вы можете перейти по ссылке на задачу.
Ссылка формируется следующим образом:
 `https://github.com/honest-hrundel/<Логин на GitHub>-<тип задачи>-task-<номер задачи>-2019`.

> :warning: Если у вас нет доступа до вашего репозитория или вам не пришло приглашение - 
напишите об этом в чат.

Для отправки решения нужно создать новую ветку и сделать из нее pull request в ветку `master`.

> :warning: Fork делать не нужно, ветку надо создать в этом же репозитории. 

## Как сделать pull request прямо на GitHub

**Шаг 1.** Заходим в основной репозиторий задачи

**Шаг 2.** Нажимаем на файл, который хотим изменить. Затем кнопку редактирования.

<img width="996" alt="edit" src="https://cloud.githubusercontent.com/assets/4534405/19143293/6f4ae788-8bbc-11e6-87c8-684037a38b22.png">

**Шаг 3.** Редактируем файл до готовности прямо здесь (или вставляем код из любимого редактора)

<img width="995" alt="progress" src="https://cloud.githubusercontent.com/assets/4534405/19143333/aa8f6d50-8bbc-11e6-9dad-9e1fccd373d1.png">

**Шаг 4.** Когда всё готово создадим коммит.   
Для этого внизу в поле вводим поясняющий текст, выбираем «Create a new branch», и нажимаем «Propose file change».

> Коммит (commit) – можно рассматривать, как утверждение кода, создание версии (как в wiki).
К каждой версии можно вернуться. Каждый новый коммит – новая версия вашего кода.

<img width="759" alt="commit" src="https://user-images.githubusercontent.com/8963033/67105208-c4035880-f1e1-11e9-874c-71b47ae90590.png">

После этого появится форма создания пулл реквеста.

**Шаг 5.** Создаем pull request.

> Пулл (pull request) - сравнение кода в личном репозитории с кодом основного.
Так мы увидим изменения, которые вы сделали. Обычно пулл затем вливают в основной репозиторий,
но мы этого делать не будем :)

<img width="759" alt="pull-request" src="https://user-images.githubusercontent.com/8963033/67105459-40963700-f1e2-11e9-9ea0-6ef3840ed72d.png">

**Готово!**

Если нужны правки, то в своем пулл реквесте нажимаем «Files changed» и повторяем шаги 2, 3 и 4, с тем единственным изменением, что
при утверждении изменений файла, нужно выбрать верхнюю опцию, тем самым сделав коммит в вашу текущую ветку. Создавать пулл реквест заново не нужно.

<img width="759" alt="edit-commit" src="https://user-images.githubusercontent.com/25838762/67197317-f5fd0080-f415-11e9-9092-dab48b21f924.png">

<img width="759" alt="edit-commit" src="https://user-images.githubusercontent.com/25838762/67145961-a268a680-f29f-11e9-809d-8502568b1b02.jpeg">

## Как сделать pull request в windows

Устанавливаем Git https://git-scm.com/download/

После установки, запускаем Git Bash  
(ярлык для запуска можно найти в меню Пуск).

Далее смотрим shell команды в разделе [как сделать pull request в linux](pull.md#Как-сделать-pull-request-в-linux).

## Как сделать pull request в linux

В linux уже установлен git и обычно настроен.

**Шаг 1.** Выполняем следующие команды в терминале:  

```bash
# Добавляем свою почту и имя (укажите из вашего профиля на github)
git config --global user.email "sergey@zhigalov.com"
git config --global user.name "Zhigalov Sergey"

# Клонируем репозиторий (вместо WisdomSpirit – ваш логин)
git clone https://github.com/honest-hrundel/WisdomSpirit-demo-task-1-2019.git

# Заходим в созданную папку с клоном
cd WisdomSpirit-demo-task-1-2019

# Создаем новую ветку, в которой будем решать задачу
git checkout -b solution

# Решаем задачу в любимом редакторе...

# Добавляем все изменённые файлы через пробел
git add math.js

# git add необходимо выполнять после каждого изменения файла

# Коммитим (утверждаем изменения)
git commit -m "Моё решение задачи"

# Отправляем ветку с коммитом в удалённый личный (origin) репозиторий
# (может попросить ввод логина и пароля)
git push origin Solution
```

**Шаг 2.** Создаём pull request

<img width="759" alt="create-pull" src="https://user-images.githubusercontent.com/25838762/67146021-17d47700-f2a0-11e9-843e-bf71aaadb59e.jpeg">

<img width="759" alt="create-pull" src="https://user-images.githubusercontent.com/25838762/67146081-b52fab00-f2a0-11e9-9f87-fd718b378d75.jpeg">

**Шаг 3.** Если нужны правки. Вносим их в любимом редакторе, и снова делаем коммит.

```bash
# Добавляем все изменённые файлы через пробел
git add math.js

# Коммитим
git commit -m "Мои исправления"

# Отправляем новый коммит в удалённый репозиторий
git push origin Solution
```
