# Telegram Grabber V2 2024
# Телеграм Граббер V2 2024
Бот позволяет пересылать весь контент с любого telegram канала (если админ канала не запретил копирование контента) на ваш канал без упоминания автора канала. Также есть возможность заменить все ссылки и упоминания в постах на ваши


# Используемые библиотеки

Для работы бота необходимо установить библиотеки.

Библиотека aiogram:

    pip install aiogram=2.25.1

Библиотека telethon:   
 
    pip install telethon

Библиотека pickle:

    pip install pickle


# Как запустить

1. Создать телеграм-бота. Для этого нужно написать боту [BotFather](https://telegram.me/botfather) и следовать инструкциям. После этого сохраните токен бота.
2. Получить api_id, api_hash. Сделать это можно на сайте [my.telegram.org](https://my.telegram.org/auth). Инструкция: https://www.youtube.com/watch?v=JBDnmEhvgac
3. Задать переменные api_id, api_hash и bot_token в файле main.py.

![image](https://user-images.githubusercontent.com/91873172/236864151-bc15d37b-d1dc-4abf-bdf7-71c8268d4d3f.png)

4. Замените на свой id аккаунта:


![image](https://github.com/WALTERXO/telegram-grabber/assets/91873172/76fa8c23-f2c2-4890-a930-6141b4fbde77)

Брать в [Get My ID](https://t.me/getmyid_bot) отсюда (отправить в бот любое сообщение, он выдаст ваш id):

![image](https://github.com/WALTERXO/telegram-grabber/assets/91873172/10a83730-3708-47d7-a134-f700ef037c4d)

Запустить бота командой:

    python main.py

**При первом запуске нужно ввести номер телефона и код, который придёт в telegram**

# Пример использования:
1. Переходим в telegram бот, который создали в начале. Вводим команду "/start", нажимаем "Добавить канал" и вводим id канала, с которого нужно брать контент. 
id нужного канала можно узнать переслав любое сообщение с канала в бот (пример id для каналов: -1001009232144) [Get My ID](https://t.me/getmyid_bot)
![image](https://user-images.githubusercontent.com/91873172/236866756-06b5a78f-0b58-45f2-a238-ce6e40550b8a.png)

2. Добавляем канал, на который должны будут приходить сообщения. Для этого жмём "Добавить канал-получатель". Бот, в котором мы всё это вводим, обязательно должен быть администратором этого канала.
3. Указываем соответсвие между каналами написав id канала-источника и id канала-получателя через пробел командой /set_channel_mapping (/set_channel_mapping -100123132890 -1000932314321). После этого перезагружаем код либо вручную закрыв и открыв компилятор кода, в котором работаем, либо по кнопке "Перезагрузить бота". **Теперь все новые сообщения, которые будут публиковать будут приходить на ваш канал.**
4. Также вам доступна команда

    /last_messages ко-во сообщений или all, если все
    
Она отправляет последние сообщения на ваш канал. Если добавили несколько каналов-источников, а последние сообщения нужны только с одного канала, то напишите

    /last_messages id канала источника ко-во сообщений

5. Режим модерации. При активации режима модерации все сообщения будут приходить сначала на ваш технический канал, в котором вы можете их редактировать, удалять и публиковать:

![image](https://github.com/WALTERXO/telegram-grabber/assets/91873172/da314d89-fc1f-4d48-885b-d801ed31df1c)

Для его работы создаём новый пустой канал и вводим id этого канала в коде (получить id можно по аналогии как с остальными каналами). Не забываем назначить бота администратором технического канала.

![image](https://github.com/WALTERXO/telegram-grabber/assets/91873172/a9ad67b1-2cc2-4967-9519-59a6e458588e)

Если вы отредактировали сообщение, то нажимайте на "Отредактировано" чтобы оно обновилось в хранилище. Возможный баг: когда в техническом канале скапливается большое количество сообщений, то при нажатии на "Отправить" может зависать. Чтобы всё заработало нажимаем на "Отредактировано", а потом "Отправить".

**Также есть возможность заменять все ссылки и упоминания, которые публикуются на каналах на ваши**. В поиске редактора кода найдите все упоминания "test" и вставь нужное вам:

![image](https://user-images.githubusercontent.com/91873172/236871594-5904f387-637a-4df4-894e-b54c3a6ab9a6.png)
Тоже самое со ссылкой:

![image](https://user-images.githubusercontent.com/91873172/236871955-47e04ae3-5db4-4f55-b2f6-f95f28b1c6e0.png)




# Список доступных команд:
* /start - Начало работы с ботом
* /help - Получить список доступных команд
* /add_channel - Добавить канал для работы
* /remove_channel - Удалить канал из списка
* /list_channels - Показать список добавленных каналов
* /add_destination_channel - Добавить канал-получатель
* /remove_destination_channel - Удалить канал-получатель из списка
* /list_destination_channels - Показать список каналов-получателей
* /set_channel_mapping - Установить соответствие между каналами
* /last_messages (ко-во сообщений или all, если все) - Отправить последние сообщения с каналов


Списки идентификаторов каналов хранятся в файле *.pickle для сохранения настроек после перезапуска бота. Отправка сооющений из технического после перезагрузки бота, когда модерация включена, слетит.



