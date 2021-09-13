# Проектирование гиперадаптивной UI-библиотеки

Это - текстовая расшифровка выступления на [FrontendConf'21](https://frontendconf.ru/moscow/2021/abstracts/7406). Вы можете [открыть в интерфейсе проведения презентаций](https://nin-jin.github.io/slides/ui-kit/), либо [читать как статью](https://github.com/nin-jin/slides/blob/master/ui-kit/readme.md)...

# Кто я такой

- 15 разработки фронтенда
- В Яндекс, 1С, Wrike, Deutche Bank, Газпром
- Автор фреймворка $mol

# План

- Размеры
- Цвета
- Раскладка
- Навигация

# Зачем? 

- Разработать с дизайнером кубики Лего
- Пилить приложения уже без дизайнера
- Выглядеть должно опрятно и в едином стиле

# Что не так с дизайнером?

- Дизайнер рисует экранчик в 3 размерах
- Согласовывает его с заказчиком
- Разрабы в шоке - это так не заработает
- Дизайнер всё перерисовывает..

# Приручаем размеры

## Базовый размер

> `1rem` (`16px`)

## Текст

![](https://hsto.org/webt/1y/z4/qm/1yz4qmvcly6let9_gs8akzdwu8k.png)

## Ширина текста

> `60rem` (`960px`)

## Межстрочный интервал

- Больше букв в строке - больше расстояние меж строк

![](https://hsto.org/webt/hg/54/5f/hg545fxfov8vm7ki6ob2rtja8w0.png)

## Визуальный ритм

> `.5rem` (`8px`)

## Дробные размеры

- Браузер рендерит пиксели
- Размеры округляются в разные стороны

## Учёт DPI

    devicePixelRatio

## Разрешение картинок

- Под размер экрана ❌
- Под плотность пикселей ❌
- Под скорость соединения ❌
- Минимум из возможных ✅

## А когда нужно гладенько?

> **Векторная графика**

## Увеличенный текст

![](https://hsto.org/webt/vd/ly/d-/vdlyd-4xwaioo1olxmo9ddjmfj4.png)

## Уменьшенный текст

![](https://habrastorage.org/webt/tj/q6/5l/tjq65l3keao6l0-chvfzp93tdcg.gif)

## Текстовый блок

![](https://hsto.org/webt/tm/we/qv/tmweqvc_b0ozqcfhxyksb-gdjvk.png)

## Блок

![](https://hsto.org/webt/zq/zy/hf/zqzyhfbqcomyomuo0iflow2jboe.png)

## Блок из блоков

![](https://hsto.org/webt/r1/hx/i4/r1hxi4vbi3b0x6da_yelxv8ja8c.png)

# Приручаем цвета

## Цветовые схемы

## Модели освещения

## Принудительное освещение

- Картинки
- Иконки
- Карты

## Хранение состояния

- Настройки браузера
- Локальное хранилище
- Ссылка

# Приручаем раскладку

## Flex переносы?

![](https://draw.hyoo.ru/#!zoom=1.6105100000000008/center=-3104362059.7893763x37276709.66794913)

## Grid переносы?

![](https://draw.hyoo.ru/#!zoom=1/center=-1927564609.4999988x23144528.5)

## Биноминальные переносы!

![](https://draw.hyoo.ru/#!zoom=0.8809690143853565/center=-1698124756.7965636x20388587.26931308)

## Маленькие таблицы..

## Большие таблицы?

## Карточки?

## Карточки с выравниванием!

## Биноминальные карточки с выравниванием!

# Приручаем экраны

## Сначала десктоп

## Сначала мобилки

## Мобильный интерфейс на десктопе

## Размеры экранов

- Их не 2
- И даже не 3
- Их континуум!

## Метафора погружения

## Буклетный дизайн

![](https://4.bp.blogspot.com/-JAYBEXzzVVo/XCcFBh1M5pI/AAAAAAAAAG4/vYOKHtoIkjgjsqNf9v0j3Sy9awpwe_iAgCLcBGAs/s1600/8.%2BBest%2BTrifold%2BBrochure%2BMockup%2BFree%2BDownload%2B2019.jpg)

## Возвращение горизонтального скролла

![](https://4.bp.blogspot.com/-LWPowjeArAM/XCcEtE1ftpI/AAAAAAAAAGY/qY-aiN7z8sY2-svA9QRWf1i8Hqc_AvQegCLcBGAs/s1600/3.%2BBest%2BTrifold%2BBrochure%2BMockup%2BFree%2BDownload%2B2019.jpg)

## Распасовка карт

![](https://2.bp.blogspot.com/-52rCts3qZ5E/XCcE4gDdJ7I/AAAAAAAAAGk/kPmTUIeyPZkzV2D3Ypz_26RuuEw4CHLGgCLcBGAs/s1600/5.%2BBest%2BTrifold%2BBrochure%2BMockup%2BFree%2BDownload%2B2019.jpg)

# Итоги

- Grid step `0.5rem` ✅
- Font size `1rem` ✅
- Break points ❌
- Binominal wrap ✅
- Tables ❌
- Aligned cards ✅
- Mobile first ❌
- Booklet design ✅

# Продолжение банкета

- [slides.hyoo.ru](https://slides.hyoo.ru/) - выступления
- [Core Dump](https://www.youtube.com/channel/UC-qEImMrqSLZ9KLee1JTcuw) - видео о компьютерной науке
- [habhub.hyoo.ru](https://habhub.hyoo.ru/) - статьи
- [apps.hyoo.ru](https://apps.hyoo.ru/) - приложения
- [`_jin_nin_`](https://twitter.com/_jin_nin_) - твиты по делу

# Есть что добавить или поправить?

![](https://habrastorage.org/webt/y3/gb/is/y3gbisydqnoyr5qwwmscn0gwmqq.gif)