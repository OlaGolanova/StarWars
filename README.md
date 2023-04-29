# Week20_API
### Вопросы 💎

1. Какие 2 обязательных шага нужно сделать до начала обращения к методам модулей?

Установить Node.js и npm. + В новом проекте npm init.


2. Как узнать, установлен ли у тебя менеджер пакетов **npm**?

npm -v  Покажет версию установленного npm 


3. Зачем нужен блок `finally`? 

Задача finally завершить начато в try до конца, даже если в try и catch использован return.


4. Есть следующий код:
    
    ```jsx
    let user = undefined;
    console.log(`Привет, ${user.name}`);
    ```
    
    Как сделать так, чтобы при обращении к нему выводилось внятное сообщение об ошибке «Имя пользователя не заполнено»?

  ```jsx
    
    let user = undefined;

    try {
        console.log(`Привет, ${user.name}`)

    } catch(err) {
        alert("Имя пользователя не заполнено" + err )
    } 

    ```

    
5. Как сгенерировать собственную ошибку, например, в случае некорректного формата данных?

 ```jsx
    
    let json = `{"id" : 2}`;

    try {
        let user = JSON.parse(json);
        if(!user.name){

            throw new Error ("В этих данных нет имени")

        }
    } catch(err) {
         console.log("Ошибка в имени:" + err.message)

    } 

    ```

6. Какую команду надо ввести, чтобы сгенерировался файл `package.json`?

npm init

7. Приведите пример захвата ошибки в случае некорректного преобразования данных:
    
    ```jsx
    console.log(parseInt('ыыыы'));
    ```

```
```jsx

    let item = 'ыыыы';
    let parseItem = parseInt(item);

    try {
        console.log(parseItem);

    if (isNaN((parseItem))){
        throw new Error ("Ошибка")
    }
    
    } catch(err) {
        console.log(err.message + err.stack )
    }

    ```


8. Изучите документацию к библиотеке moment [https://momentjs.com/](https://momentjs.com/) и скажите, как вывести название дня недели по дате?

let day = moment().format('dddd');// Saturday


