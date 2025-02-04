# js1-second
Конспект: TDZ, Scope и Hoisting в JavaScript
1. Scope (Область видимости)
Scope – это правила, которые определяют, где в коде можно обращаться к переменным.
Есть три типа областей видимости:

Глобальная область: Переменные доступны в любом месте программы.
Функциональная область: Переменные доступны только внутри функции, где они объявлены.
Блочная область: Переменные, объявленные через let или const, доступны только внутри блока { ... }.
Пример:

javascript
Копировать код
function example() {
    let x = 10; // Переменная видна только внутри этой функции
    console.log(x); // Работает
}
console.log(x); // Ошибка, x не виден
2. Hoisting (Поднятие)
Hoisting – это механизм, при котором объявления переменных и функций "поднимаются" в начало своей области видимости.

Переменные, объявленные через var, поднимаются, но не инициализируются.
let и const тоже поднимаются, но их нельзя использовать до объявления (из-за TDZ).
Функции можно вызывать до их объявления.
Пример:

javascript
Копировать код
console.log(a); // undefined (объявление поднято, но значение ещё не присвоено)
var a = 5;

console.log(b); // Ошибка (переменная в TDZ)
let b = 10;
3. TDZ (Temporal Dead Zone)
TDZ – это время между "поднятием" переменной и её фактическим объявлением.
Если попытаться обратиться к переменной в TDZ, будет ошибка.

Это относится только к let и const.
var не имеет TDZ.
Пример:

javascript
Копировать код
console.log(x); // Ошибка (TDZ для x)
let x = 5;

function test() {
    console.log(y); // Ошибка (y в TDZ)
    const y = 10;
}
Главное запомнить:
Scope: Определяет, где видна переменная.
Hoisting: Переменные "поднимаются", но не всегда доступны до объявления.
TDZ: Временная зона, где переменные let и const недоступны до их объявления.
