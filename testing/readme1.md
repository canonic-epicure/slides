# todo

- начало июня
- сконцентрироваться на фракталах
- пруфы из жизни

# Новелла о прагматичном тестировании

- О себе
- О своём пути
- О цели выступления

Вы можете [открыть в интерфейсе проведения презентаций](https://nin-jin.github.io/slides/testing/)

# Типичные проблемы разработки

- Баги
- Деньги
- Сроки
- Менеджеры

# Борьба с багами

- Пиши без багов! (с) Наивный Тимлид
- Поднять отряд ручных тестировщиц! (c) Типичный Менеджер
- Опишем всё типами! (с) Читатель Хабра
- Кажется нам нужны тесты.. (с) Безысходность

# Виды контрактов

- На словах
- На типах
- На примерах

# Нелюбовь к тестам

- Долго писать
- Сложно писать
- Всё время ломаются
- Бесполезны

## Долго писать

- Медленный запуск
- Много кода
- Много кейсов
- Сложно писать

## Сложно писать

- Нетестируемая архитектура
- Ограниченный тестовый фреймворк

## Всё время ломаются

- Меняются требования
- Меняется понимание требований
- Фиксируется неважное поведение

## Бесполезные тесты

- Проверяют не важное поведение
- Не проверяют важное поведение
- Недостаточный охват

## Недостаточный охват

- Разработчики не умеют в тестирование
- Вредные практики (TDD, GWT)
- Лень

# Идеальные тесты

- Проверяют лишь важное
- Не фиксируют неважное
- Минимальное число
- Охватывают все кейсы
- Исполняются быстро
- Писать просто

# Зачем? Обнаружение дефектов как можно раньше!

> *Жизненный цикл фичи: dev -> review -> qa -> uat -> prod*
> *Чем раньше поставить тесты, чем короче цикл отладки.*

# Зачем? Локализация дефектов!

> *Тест указывает на конкретное проблемное место в коде.*

# Зачем? Ускорение разработки!

> *Тест в любом случае придётся написать.*
> *Но перезапускать его быстрее, чем проверять руками.*

# Зачем? Актуальная документация!

> *Отдельная документация всегда врёт.*
> *Даже если это комментарий рядом с кодом.*

# Объект тестирования: система (приложение)

Система - едница развёртывания.

![Система](https://habrastorage.org/webt/c7/4_/sz/c74_szrrneggxzrhhlfmjcq9oii.png)

# Объект тестирования: модуль (юнит)

Модуль - единица кода.

![Модули](https://habrastorage.org/webt/5z/u8/vy/5zu8vyrvkhqjasajsfojyjle_ys.png)

# Объект тестирования: компонент (подсистема)

Компонент - единица функциональности.

![Компоненты](https://habrastorage.org/webt/tj/7k/d0/tj7kd0ziamst1l_8sumfrbp42ke.png)

# Игра про объекты

Игра для слушателей: индивит-команда-отдел-компания-холдинг.

# Тип теста: функциональный

> *Чёрный ящик.*
> *Пример: тыкнули палочкой - он сказал "ой".*

# Тип теста: интеграционный

> *Соединённая группа чёрных ящиков.*
> *Пример: парсер + сериализатор.*

# Тип теста: нагрузочный

> *Маленький чёрный ящик боится в окружении танков.*
> *Пример: 1000 раз тыкнули палочкой и замерили время последнего "ой".*

# Вид процесса тестирования: приёмочный

> *Выбраковка на конвеере.*

# Вид процесса тестирования: регрессионный

> *Тут поправил - там поехало.*

# Вид процесса тестирования: дымовой

> *Просто Дженга.*

# Вид процесса тестирования: полный

> *Детальные замеры болта.*

# Вид процесса тестирования: конфигурационный

> *~~Секс~~ Программирование в разных местах.*

# Классификация тестирования

| Процесс | Тип | Объект |
|---------|-----|--------|
| Приёмочная проверка.. | ..функциональности.. | ..модуля. |
| Регрессионная проверка.. | ..интеграции.. | ..компонента. |
| Дымовая проверка.. | ..производительности.. | ..системы. |
| Полная проверка.. | | |
| Конфигурационная проверка.. | | |


# Полнота тестирования: позитивные сценарии

```typescript
function isEquilateral(
    ... sides : [
        number,
        number,
        number,
    ]
) {
    sides.sort( compareNumbers ) 
    const [ a , b , c ] = sides
    return a === c
}
```

| a | b | c | isEquilateral
|---|---|---|--------------
| 2 | 2 | 2 | true
| 3 | 2 | 2 | false

Это чёрный ящик

# Полнота тестирования: ветки логики

```typescript
function isEquilateral(
    a: number,
    b: number,
    c: number,
) {
    return ( a === b )&&( b === c )
}
```

| branch | a | b | c | isEquilateral
|--------|---|---|---|--------------
| first | 1 | 2 | 2 | false
| second | 2 | 2 | 1 | false
| second | 2 | 2 | 2 | true

Белый ящик даёт лучшее покрытие

# Полнота тестирования: негативные сценарии

| a | b | c | isEquilateral
|---|---|---|--------------
| 0 | 2 | 2 | 🔥

## Классы эквивалентности

| a          | b | c | isEquilateral
|------------|---|---|----------------
| [ -∞ .. 0 ] | 2 | 2 | 🔥
| ( 0 .. 4 ) | 2 | 2 | false
| [ 4 .. +∞ ] | 2 | 2 | 🔥

## Граничные условия

```
NaN
-∞
0
δ
a + b - δ
a + b
+∞
```

# Соотношение тестов к коду

Полное покрытие - не менее **11** тестов

| a | b | c | isEquilateral
|---|---|---|--------------
| -∞ | 2 | 2 | 🔥
| 0 | 2 | 2 | 🔥
| δ | δ | δ | true
| δ | 2 | 2 | false
| 2 | 2 | 2 | true
| 3 | 2 | 2 | false
| 4 - δ | 2 | 2 | false
| 4 - δ | 4 - δ | 4 - δ | true
| 4 | 2 | 2 | 🔥
| ∞ | 2 | 2 | 🔥
| NaN | 2 | 2 | 🔥

# Суть TDD

![Pure TDD](https://habrastorage.org/webt/nx/wy/ye/nxwyyetapmska5zuvikeaiw7yww.png)

# Блеск и нищета TDD

```typescript
function checkedSide( a :  number ) {
    if( a > 0 && Number.isFinite(a) ) return a
    throw 'wrong input'
}

function isEquilateral(
    ... sides : [ number , number , number ]
) {
    const [ a , b , c ] = sides.map( checkSide ).sort( compareNumbers )
    if( c >= a + b ) throw 'wrong input'
    return a === c
}
```

После 5 цикла тесты будут сразу зелёные

# Правильный TDD - не TDD

![Fixed TDD](https://habrastorage.org/webt/j_/vt/33/j_vt33_3ez3jonfpekqyoddttgc.png)

# Когда тесты лишние

- Когда требования не ясны
- Когда дохода дают меньше, чем расходов

Переписывать код - обидно. Переписывать тесты - обидно вдвойне.

# Тестирование в большинстве компаний

1. Разработчики пишут модульные тесты.
2. Приёмочное/регрессионное ручное тестирование при релизе.
3. Автотестеры с сильной задержкой пишут системные тесты.

# Модульные тесты ломают инкапсуляцию

> *Модуль А зависит от модуля Б.*
> *Зависимость от Б выносится в публичный интерфейс.*
> *Часто это знание навязывается через конструктор.*
> *Инкапсуляция не про сокрытие внутренних полей, а про незнание внутренних особенностей.*

# Модульные тесты - хрупкие

> *Модуль А зависит от модуля Б.*
> *Изменили протокол их взаимодействия, не меняя внешнего поведения А.*
> *Сломались тесты А и Б.*

# Модульные тесты не полны

> *Чем меньше и проще модули, тем более важно их взаимодействие.*

# Интеграционные тесты не полны

> *То, что они могут взаимодействовать правильно, не значит, что оно так и есть в конечном приложении.*

> 1 + ( 2 * 3 ) = 7
> ( 1 + 2 ) * 3 = 9

# Системные тесты не масштабируются

> *Тестрование самолёта в сборе, чтобы проверить, что шуруп подходит к гайке.*

> ( b * b ) + ( -4 * a * c )

# Правда про интеграционные тесты

1. Их никто на самом деле не пишет.
2. А те, кто пишет, пишет на самом деле компонентные.

# Компонентные тесты

1. Медленные (TestBed в ангуляре давал 100мс на тест)
2. Не локализуют проблему (часто запускаются в поизвольном порядке)
3. Невозможны в монолитной архитектуре

# Рожок тестирования

![Пирамида и рожок тестирования](https://habrastorage.org/webt/ep/iv/4k/epiv4k-gp9lfbunqemk8yom2qu4.png)

Хватит вращать рожок тестирования, его нужно просто выбросить.

# Фрактальные тесты

> *Компонентных тестов столько же сколько модульных*
> *писать их проще чем модульные*
> *исполняются они быстрее чем системные*
> *а покрытие дают сравнимое с системным*

# Резюме

- Разработчики не знают как тестировать
- Белый ящик предпочтительнее чёрного
- Фиксировать надо важное поведение
- А невавжное фиксироваться не должно
- Тесты нужны самому же разаботчику
- TDD фундаментально непригоден
- Модульные тесты бессмысленны
- Фрактальные тесты наиболее практичны