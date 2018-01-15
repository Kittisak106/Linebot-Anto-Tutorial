# Linebot-AntoIO Tutorial

## Getting Started
#### Follow my tutorial on medium.com (Thai)
https://medium.com/@isaradream/linebot-anto-io-tutorial-c9e5126409b9
#### Or Following these steps
- Create your [Anto](https://www.anto.io/) account

- **"Anto"** Create your things, channels and generate key from [Anto](https://www.anto.io/)

- Create "Line@ account"

- Enable the messaging api and allow webhooks

- Get your "Channel Secret" and "Channel Access Token" from "Line Developers" (Channels->Basic information)

- Create your [Heroku](https://www.heroku.com/) account

- Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)

- Clone this repository
```
  $ git clone https://github.com/DreamN/Linebot-Anto-Tutorial.git
```

- Replace your Anto(username, key, thing) and LineMessagingApi(Channel Secret, Channel Access Token) with the same name in [app.py](https://github.com/DreamN/Linebot-Anto-Tutorial/blob/master/app.py)

- Coding your bot to do somethings
Ex.
```python
@handler.add(MessageEvent, message=TextMessage)
def handle_message(event):
    message = event.message.text
    if(message == 'channel1 on'):
        anto.pub('myChannel1', 1)
        line_bot_api.reply_message(
            event.reply_token,
            TextSendMessage(text="Turn On channel1"))
    elif(message == 'channel1 off'):
        anto.pub('myChannel1', 0)
        line_bot_api.reply_message(
            event.reply_token,
            TextSendMessage(text="Turn Off channel1"))
    elif(message == 'channel2 on'):
        anto.pub('myChannel2', 1)
        line_bot_api.reply_message(
            event.reply_token,
            TextSendMessage(text="Turn On channel2"))
    elif(message == 'channel2 off'):
        anto.pub('myChannel2', 0)
        line_bot_api.reply_message(
            event.reply_token,
            TextSendMessage(text="Turn Off channel2"))
```

- Create Heroku Apps
```
  $ heroku create
```
- Commit your changes
```
  $ git add .
  $ git commit -m "My Commit Message"
```
- Deploy to heroku
```
  $ git push heroku master
```
- Edit your webhook's url on your bot's basic information on "Line Developers" with your heroku apps url + '/callback' (https://yourapp.herokuapp.com/callback)

- Have fun!!


## Reference
```
  https://github.com/line/line-bot-sdk-python
```
"# LineControl" 
# LineControl
