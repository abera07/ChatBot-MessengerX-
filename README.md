# Machaao PHP Sample Bot

**messengerx-php-sample** : This is an echo bot which shows the basic usage
of the MACHAAO send message API, it contains the php code base to
get you started

Register your bot url
---------------------

Contact us for registering your bot url and we will issue you an
api\_token (connect@machaao.com)

Install NGROK - For Dynamic DNS (Required)
------------------------------------------

* Install ngrok for your OS via https://ngrok.com/download.
* Run ngrok on port 5005 with the following command, and note the generated https url

``` 
ngrok http 5005 
```

Run your PHP script
-------------------
* Clone the php script from the repo https://gitlab.com/solutionfuse-randd/messengerx-php-sample.git
* Move to your root directory
* run 
``` 
php -S localhost:5005 
``` 
this will start the php webserver in 
``` 
port 5005 
```

### Update your webhook ###
---------------------------

Update your bot url on MACHAAO with the NGROK url provided as shown below to continue development
```
curl --location --request POST 'https://ganglia-dev.machaao.com/v1/bots/<YOUR API-TOKEN> \
--header 'api_token: <YOUR API-TOKEN>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "<YOUR URL>/mahaao_hook.php",
    "description": "<YOUR BOT DESCRIPTION>",
    "displayName": "<YOUR BOT NAME>"
    }'
```

# Run on Heroku #
-----------------
We are assuming you have access to a [heroku account](https://heroku.com)
and have installed heroku command line client for your OS.

# Login to Heroku #
-------------------
```
heroku login
```
Create a new app on Heroku and note down your heroku app name

### Deploy the app ###
```
heroku create
```
Create an app on Heroku, which prepares Heroku to receive your source code

Now deploy your code

```
git push heroku master
```

### View Heroku logs ###

```
heroku logs --tail
```
Heroku treats logs as streams of time-ordered events aggregated from the output streams of all your app and Heroku components, providing a single channel for all of the events.

## Update your webhook ##
-------------------------
Update your bot url on MACHAAO with the heroku url as shown below to continue development
```
curl --location --request POST 'https://ganglia-dev.machaao.com/v1/bots/<YOUR API-TOKEN> \
--header 'api_token: <YOUR API-TOKEN>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "<Your_Heroku_App_Name>.herokuapp.com/machaao_hook.php",
    "description": "<YOUR BOT DESCRIPTION>",
    "displayName": "<YOUR BOT NAME>"
    }'
```

