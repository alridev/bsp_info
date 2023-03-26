# Документация

#### Во-первых, пробегусь по тому, что за детище.

> **Что такое $BSP?**
> > это парсер seed-фраз, wif-ключей и hex-ключей

> **Какие языки seed-фраз поддерживает?** 
> >  english
> >   chinese_simplified
> >   chinese_traditional
> >  french
> >  italian
> >   japanese
> >   korean
> >   spanish

> **Какой тип seed-фраз по кол-ву слов парсит?**
>> 12, 15, 18, 21, 24

>**Что чекает?**
>> TDATA, Telethon *.session

>**Чекает он seed-фразы?**
>> Нет, но уже в планах на будущее...

> **Какие файлы парсит?**
>> ВСЕ, в настройках можно указать какие нужно парсить, какие нет. Также он читает docx, pdf и odt
___

#### Во-вторых, настройки.
При запуске, если файл config.ini не был найден в папке с программой, она создаст его с стандартными настройками.
**Теперь разберёмся**
 
**`параметр - тип - описание`**
  


    
    
    [ОСНОВНЫЕ]
    тип_работы - число - это тип работы $BSP. Всего типов 5: 
											    1-чек тадат
											    2-чек сессий
											    3-парсинг тадат
											    4-парсинг сессий
											    5 парсинг файлов
	папка_данных - строка - Путь до данных (логов). 
	    По дефолту ./data$bsp, но если папка с логами за пределами папки с программой, требуется полный путь.
	    При ошибке (root path not found) - смотреть правильно ли вы написать путь
    
    [ЧЕК_ТЕЛЕГРАММ]
    копировать_валид - булево выражение - После чека тдат или сессий скопируются в папку *.valid$bsp.
    True - да
    False - нет
    сохранять_данные_телеграмм - булево выражение - После чека тдат или сессий данные каждого аккаунта сохранятся в файл data.telegram$bsp.txt.
    True - да
    False - нет
    формат_данных_телеграмм - строка - Пример:
							@{username} {phone} {path} это будет @nickname 88005353535 /path/to/tdata
											    path - путь до тадаты или сессии
											    username - никнем
											    phone - телефон
											    id - ID аккаунта
											    first_name - Имя
											    last_name - Фамилия
											    deleted - удален ли аккаунт
											    lang_code - язык аккаунта
											    premium - есть ли премиум
											    scam - скам или нет
												verified - верифицирован или нет
	
    заменять_когда_нет_ника - строка - на что заменить, когда у пользователя нет ника, если ничего не делать: {username}
    макс_время_работы_потока - число - ограничение работы в секундах. Сколько поток может быть запущен
    макс_потоков - число - максимальное кол-во потоков
    
    [ПАРСИНГ_ТЕЛЕГРАММ]
    макс_время_работы_потока - число - ограничение работы в секундах. Сколько поток может быть запущен
    макс_потоков - число - максимальное кол-во потоков
    парсить_сидки - булево выражение - парсить ли сидки
    парсить_виф_ключи - булево выражение - парсить ли wif-ключи
    парсить_хекс_ключи - булево выражение - парсить ли hex-ключи
    
    [ПАРСИНГ_ФАЙЛОВ]
    макс_размер_файлов - число - максимальный размер файла в мигабайтах
    макс_время_работы_потока - число - ограничение работы в секундах. Сколько поток может быть запущен
    макс_потоков - число - максимальное кол-во потоков
    черный_список_файлов - список - ['*.exe', '*.dll', '*.расширение'] - если не использовать []
    белый_список_файлов = - ['*.txt', '*.pdf', '*.расширение'] - если не использовать [] - все кроме тех которые в чёрном списке 
    парсить_сидки - булево выражение - парсить ли сидки
    парсить_виф_ключи - булево выражение - парсить ли wif-ключи
    парсить_хекс_ключи - булево выражение - парсить ли hex-ключи
