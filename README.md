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
    "url": "<YOUR URL>/webhooks/machaao/incoming",
    "description": "<YOUR BOT DESCRIPTION>",
    "displayName": "<YOUR BOT NAME>"
    }'
```

