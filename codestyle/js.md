# Оформление JavaScript кода

Часть правил оформления будет проверена автоматически,  
на остальные обратят внимание менторы во время ручной проверки.

Ознакомиться с механизмом вы можете на демонстрационной задаче:  
`https://github.com/honest-hrundel/<Логин на GitHub>-demo-task-1-2019`

- [Правила для автоматической проверки](#Правила-для-автоматической-проверки)
- [Не пишите код впрок](#Не-пишите-код-впрок)
- [Не повторяйтесь](#Не-повторяйтесь)
- [Пишите проще](#Пишите-проще)
- [Называйте переменные понятно](#Называйте-переменные-понятно)

## Правила для автоматической проверки

Когда вы отправляет pull request, ваш код автоматически проходит проверку  
на соответствие этим правилам при помощи специального анализатора кода –  [eslint](http://eslint.org/docs/rules/).

В случае, если проверка прошла, вы увидите комментарий:
<img width="769" alt="fail" src="https://user-images.githubusercontent.com/25838762/67099166-e2178b80-f1d6-11e9-9c81-c25b33265242.png">


Чтобы узнать какие именно правила были нарушены:
1. Установите зависимости для тестов командой `npm run deps` или `npm ci`
2. Запустите проверку качества кода `npm run test`
3. ESlint покажет список нарушений с указанием файлов и строк в них
4. Сверяясь со [справкой](http://eslint.org/docs/rules) исправьте все нарушения

Если код удовлетворяет всем правилам, то запустятся внутренние тесты
и появится комментарий о количестве пройденных тестов.

 <img width="769" alt="fail" src="https://user-images.githubusercontent.com/25838762/67101419-04aba380-f1db-11e9-9ca5-53ff4540cd13.png">
 
 или

 <img width="769" alt="success" src="https://user-images.githubusercontent.com/8963033/67101462-1ab96400-f1db-11e9-9e44-18a3e1ea52be.png">

## Не пишите код впрок

Следуйте приниципу [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it) (You ain't gonna need it) – не пишите код, который не понадобится вам для решения задачи. Если все проверки и тесты пройдены, значит кода уже достаточно – потратьте время на рефакторинг.

__Плохо:__

```js
// My awesome math utils
function sum(numbers) {}
function average(numbers) {}
function median(numbers) {}

sum([1, 2, 3]);
// 6
```

__Хорошо:__
```js
function sum(numbers) {}

sum([1, 2, 3]);
// 6
```

## Не повторяйтесь

Следуйте приниципу [DRY](https://ru.wikipedia.org/wiki/Don%E2%80%99t_repeat_yourself) (Don’t repeat yourself) – не пишите похожий код несколько раз,   
старайтесь его переиспользовать.

__Плохо:__
```js
let averageRating = ratings
    .reduce((sum, rating) => sum + rating, 0) / ratings.length;

let averageGrade = grades
    .reduce((sum, grade) => sum + grade, 0) / grades.length;
```

__Хорошо:__
```js
function getAverageOf(numbers) {}

let averageRating = getAverageOf(ratings);
let averageGrade = getAverageOf(grades);
```

## Пишите проще

Следуйте приниципу [KISS](http://people.apache.org/~fhanik/kiss.html) (Keep it short and simple) – пишите проще   
и по полной используйте все возможности языка.

__Плохо:__
```js
let numbers = [1, 4, 5, 2, 3];

// Сортируем числа
// TODO: оптимизировать – может быть быструю сортировку?
for (let i = 0; i < numbers.length; i++) {
    for (let j = 0; j < numbers.length; j++) {
        if (numbers[j] > numbers[j+1]) {
            const greatest = numbers[j];

            numbers[j] = numbers[j+1];
            numbers[j+1] = greatest;
        }
    }   
}
```

__Хорошо:__
```js
let numbers = [1, 4, 5, 2, 3];

numbers.sort()
```

## Называйте переменные понятно

1. Используйте [camelCase](https://en.wikipedia.org/wiki/CamelCase)

    __Плохо:__
    ```js
    let apples_count = 5;
    let Language = 'ru';
    ```

    __Хорошо:__
    ```js
    let applesCount = 5;
    let language = 'ru';
    ```

2. Используйте только английские слова, не используйте транслит

    __Плохо:__
    ```js
    let ssilka = 'http://esling.org/';
    let ссылка = 'http://esling.org/';
    ```

    __Хорошо:__
    ```js
    let link = 'http://esling.org/';
    ```

3. Вкладывайте смысл в название – оно должно быть однозначным и понятным

    __Плохо:__
    ```js
    let a, b; // Не несут смысла
    let list; // Слишком абстрактно – список чего?
    ```

    __Хорошо:__
    ```js
    let overallPrice, publishDate;
    let grocceryList;
    ```

    Допустимо использовать `i`, `j` в качестве итераторов цикла `for (let i = 0; i < 2; i++) {}`,  
    и `a`, `b` – в функциях сортировки `grocceryList.sort(function (a, b) {})`

4. Логические перменные начинайте с модальных глаголов

    __Плохо:__
    ```js
    let accessToPublish
    let visible;
    ```

    __Хорошо:__
    ```js
    let canPublish
    let isVisible;
    ```

5. Не используйте сокращения и не пишите избыточные имена

    __Плохо:__
    ```js
    let btn;
    let dateOfFirstPublication;
    let postsCollection;
    ```

    __Хорошо:__
    ```js
    let button;
    let publishDate;
    let posts;
    ```

6. Объявляйте переменные максимально близко к месту использования

    __Плохо:__
    ```js
    let hasAccess = hasAccess(); // Далеко от места использования
    let comments = getComments();
    let overalRaiting = 0;

    for (let i = 0; i < comments.length; i++) {
        overallRating += comments[i].rating;
    }

    if (hasAccess) {
        show(overallRating);
    }
    ```

    __Хорошо:__
    ```js
    let comments = getComments();
    let overalRaiting = 0;

    for (let i = 0; i < comments.length; i++) {
        overallRating += comments[i].rating;
    }

    let hasAccess = hasAccess();

    if (hasAccess) {
        show(overallRating);
    }
    ```

7. Для именования функций используйте глаголы

    __Плохо:__
    ```js
    function length() {}
    function title(name) {}
    function visible() {}
    ```

    __Хорошо:__
    ```js
    function getLength() {}
    function setTitle(name) {}
    function isVisible() {}
    ```
