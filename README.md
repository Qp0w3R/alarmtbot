# Bot Smart Scheduler

## Links

- [English version](README-EN.md)

## На данный момент бот распознает только время, написанное на русском языке.

Если вам нужно быстро и с удобством планировать свои задачи, бот Smart Scheduler станет незаменимым инструментом в этом деле.

![Пример использования](https://habrastorage.org/webt/03/ie/sd/03iesdxbqwrpwrkoxtl3ibmtkfs.png)

## Как использовать

[Бот Smart Scheduler работает в Telegram.](https://t.me/SmartScheduler_bot)
Просто напишите задачу и требуемое время, а Smart Scheduler автоматически найдет дату и задачу в сообщении.
По истечению времени запланированной задачи бот Smart Scheduler пришлет вам уведомление.

Данный бот распознает большинство форм представления даты человеком (например «через X минут», «без пятнадцати десять», «послезавтра пол первого»), поэтому вам не нужно следовать определенному формату времени.

## Особенности

Smart Scheduler способен записывать время с точностью _до минуты_.  
Smart Scheduler хранит для каждого чата задачи **раздельно** и может функционировать в беседах.  
Smart Scheduler может формировать напоминания из голосовых сообщений.  

### Поддерживаемые комманды:

- 🗓 **/list** - Показывает активные задачи для данного чата.

- 🗑 **/del** _1, 2, ...N_ - Удаляет задачи по id.

- 🗑 **/del** _1-10, A-B_ - Удаляет задачи в введенном диапазоне.

- #️⃣ **_/N_** - Удаляет N-ную задачу.

- 🌐 **_/tz_** - Настройка часового пояса.

- 🎛 **_/kb_** - Открыть меню.

и конечно же /start и /help.

## Установка

Для работы бота требуется база данных PostgreSQL.  

### Переменные среды

Прежде чем запускать бота, убедитесь что вы установили следующие переменные среды:  
**ENABLE_LOGS**: "true" или "false", включает или отключает логирование.  
**ENABLE_SCHEDULES_CHEKING**: "true" или "false", включает или отключает проверку и отправление уведомлений.  
**TZ**: только "GMT".  
**DATABASE_URL** (опционально): URL базы данных PostgreSQL.  
**SMART_SCHEDULER_DB_URL** (опционально): URL базы данных PostreSQL.  
**IS_HEROKU**: "true" или "false". Если **true**, то для базы данных используется **DATABASE_URL**, иначе **SMART_SCHEDULER_DB_URL**.  
**SMART_SCHEDULER_TLGRM_API_TOKEN**: токен бота в телеграмме.  
  
Для голосовых сообщений (опционально):  
**YC_API_KEY**: Yandex api key.  
**YC_FOLDER_ID**: Yandex catalog id.  
Если не укзаать эти переменные, то бот не будет отвечать на голосовые сообщения.  

### На локальном сервере

```
$ git clone https://github.com/alordash/BotSmartScheduler
$ cd BotSmartScheduler
$ npm install
$ node ./BotCode/index.js
```

### Используя heroku

1. Создайте аккаунт [github](https://github.com/join).  
2. Добавьте [этот](https://github.com/alordash/BotSmartScheduler) репозиторий к себе.  
3. Создайте аккаунт [heroku](https://signup.heroku.com/).  
4. Создайте новое [heroku приложение](https://dashboard.heroku.com/new-app).  
5. Откройте новое приложение.  
6. Перейдите по [этой ссылке](https://elements.heroku.com/addons/heroku-postgresql).  
7. Нажмите **Install Heroku Postgres**.  
8. В появившейся строке введите название своего приложения и нажмите **Provision add-on**.  
9. Перейдите во вкладку **Settings** своего приложения.  
10. Нажмите **Reveal Config Vars**.  
11. Заполните все необходимые переменные среды.  
12. Перейдите во вкладку **Deploy**.  
13. В поле **Deployment method** выберите **GitHub**.  
14. Подключите свой github аккоунт к хероку нажав **Connect to GitHub**.  
15. В появившемся окне выберите *ваш* репозиторий, нажмите **connect**.  
16. Нажмите **Deploy Branch**.  
17. После окончания загрузки перейдите во вкладку **Resources**.  
18. Отключите **web**, включите **worker**.  
Теперь вы можете попробовать написать вашему боту.