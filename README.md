# telegram-echo-bot
This is a simple telegram bot that that responds to user messages with (user message + "over"). 
For Deploying it you can use any serverless solution (eg. Cloudflare Workers )
## Deploying :
### I. Create a new Cloudflare Worker
Navigate to dash.cloudflare.com and login (or sign up).On the sidebar, click on ‘Workers’.Click on ‘Create a service’ to create your new worker.Enter a name for your new worker and select the ‘HTTP handler’ as the starter, and click on ‘Create service’. Once your service has been created, click on ‘Quick Edit’ to edit your worker directly in the browser.
### II. Copy The Contents of worker.js from this repository and click on save and deploy.
### III. Create The Bot using @botfather on telegram and get the API Token for your bot.
### IV. Set Your Bot's API Key in Cloudflare Worker
Go back to the your worker’s dashboard. Under the settings panel, click on variables and Click on ‘Add variable’ and input the variable name as API_KEY and the value as the bot’s API token and save your settings.
### V. Set The Webhook
Copy your bot API token and your worker url (found on the right side of the worker preview page on Cloudflare dashboard) in this Link and paste it in your browser
```
https://api.telegram.org/bot<YOUR_BOT_API_TOKEN_GOES_HERE>/setWebhook?url=<YOUR_WORKER_URL_GOES_HERE>
```
If you see this as a response, you’re good to go!
```
{"ok":true,"result":true,"description":"Webhook was set"}
```
now if you message to your bot in telegram, the bot will respond with your message and adds "over" in the end.
