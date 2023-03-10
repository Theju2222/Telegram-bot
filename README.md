TELEGRAM BOT

### Setup

1. Install package from pip:  
    ```
    pip install django-tgbot
    ```

2. Add `django_tgbot` to your Django project's `INSTALLED_APPS`

That's it :) You installed django-tgbot.

<hr>

### Create a new Telegram bot
1. Create a bot in Telegram using [BotFather](https://t.me/BotFather) and receive your API token
2. Open the Django project with `django-tgbot` installed in it
3. Enter this command in the command line (terminal / cmd):
    ```
    python manage.py createtgbot
    ```
4. Enter your API token:
    ```
    > python manage.py createtgbot
    Enter the bot token (retrieved from BotFather): <YOUR_TOKEN>
    Setting up @BotDevTestBot ...
    ```
5. Enter the URL your Django project is deployed on. If your project is not deployed yet and is not accessible, press Enter to skip. (If you have not deployed yet and want to test your bot, you can use services like [Ngrok](http://ngrok.com) to do so)
    ```
    Enter the url of this project to set the webhook (Press Enter to skip): https://URL.com
    Bot webhook will be set to https://URL.com/botdevtestbot/update/. Do you confirm? (Y/N): y
    Webhook was successfully set.
    ```

6. A new app will be created in your Django project. Add this app to your `INSTALLED_APPS`
7. Include this new app's urls in your project urls as described in the output of the above command
8. Update the database:
    ```
    python manage.py migrate
    ```

Your bot is created! If you have set the webhook correctly you can now send messages to your bot and it responds all messages with `Hello!`.

<b> Overview of the process: </b>

```
> python manage.py createtgbot
Enter the bot token (retrieved from BotFather): 521093911:AAEe6X-KTJHO98tK2skJLsYJsE7NRpjL8Ic
Setting up @BotDevTestBot ...
Enter the url of this project to set the webhook (Press Enter to skip): https://URL.com
Bot webhook will be set to https://URL.com/botdevtestbot/update/. Do you confirm? (Y/N): y
Webhook was successfully set.
Successfully created bot Test Bot(@botdevtestbot).
Next steps:
	1. Add 'botdevtestbot' to INSTALLED_APPS in project settings
	2. Add `from botdevtestbot import urls as botdevtestbot_urls` to project urls file
	3. Add `path('botdevtestbot/', include(botdevtestbot_urls))` to project urls' urlpatterns
	4. `python manage.py migrate`
Enjoy!
```
