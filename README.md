from telethon import events , TelegramClient
from asyncio import sleep as zzz
from random import randint
from re import match

#dont edit else gay this constant
api_id = 20505295
api_hash = '1c6a034a689bf4bd9c6a6c6886f68369'
bot = TelegramClient('session' , api_id , api_hash)
chat = 572621020

#edit the list
list = ["Riolu" , " Munchlax" ,  "Gastly" , "Lopunny" ," Gallade" , "Starly" ,  "Arceus" , "Darkrai" , "Palkia" ,  "Scizor" , "Heatran" , "Regigigas" , "Blissey" , "Porygon-Z" , "Giratina" ,"Dialga" "Absol"]


@bot.on(events.NewMessage(outgoing=True,pattern='.go'))
async def begin(event):
    global hunt
    hunt = True
    x = await bot.send_message(chat , "/hunt")
    try:  
     async with bot.conversation('@Hexamonbot') as conv:
       await conv.get_response(x.id)
    except:
       await zzz(1,3)
       await bot.send_message(chat , "/hunt")
    for i in range(1,10000):
      await zzz(randint(1000, 1020))
      await bot.send_message(chat , "/hunt")

@bot.on(events.NewMessage(chats=chat,incoming=True))
async def hunt(event):
    if hunt == True:
     text = event.message.text
     hun = True
     message = await bot.get_messages(chat, ids=event.message.id)
     if ("A shiny" in text):
        bot.disconnect()
     elif ("Arceus" in text):
       bot.disconnect()
     elif("TM" in text):
        print(event.message.text)
        await zzz(randint(1,3))
        x = await bot.send_message(chat , "/hunt")
        try:  
         async with bot.conversation('@Hexamonbot') as conv:
           await conv.get_response(x.id)
        except:
           await zzz(1,3)
           await bot.send_message(chat , "/hunt")
   #  elif any(item in text for item in list):
     elif True:
        await message.click(text="Battle")
        await message.click(text="Battle")
        await message.click(text="Battle")
     elif("A wild" in text or "An expert" in text):
      if hun == False:
       pass
      else:
       await zzz(randint(2,5))
       x = await bot.send_message(chat , "/hunt")
       try:  
        async with bot.conversation('@Hexamonbot') as conv:
          await conv.get_response(x.id)
       except:
          await zzz(1,3)
          await bot.send_message(chat , "/hunt")
      

@bot.on(events.NewMessage(chats=chat,incoming=True))
async def hunt(event):
   print(event.message.text)
   if event.message.text[:13] == "Battle begins":
        message = await bot.get_messages(chat, ids=event.message.id)
        await zzz(2)
        await message.click(text = "Poke Balls")
        await message.click(text = "Poke Balls")
        await message.click(text = "Poke Balls")      


@bot.on(events.MessageEdited(chats=chat))
async def cacther(event):
   message = await bot.get_messages(chat, ids=event.message.id)
   await message.click(text = "Poke Balls")
   await message.click(text = "Poke Balls")
   await message.click(text = "Poke Balls") 
   if event.message.text[:4] == "Wild":
      await zzz(2)
      await message.click(text = "Regular")
      await message.click(text = "Regular")
      await message.click(text = "Regular")
   if any(keyword in event.message.text for keyword in ['fled', 'fainted', 'caught']):
      await zzz(randint(2,5))
      x = await bot.send_message(chat , "/hunt")
      try:  
       async with bot.conversation('@Hexamonbot') as conv:
         await conv.get_response(x.id)
      except:
         await zzz(1,3)
         await bot.send_message(chat , "/hunt")



@bot.on(events.NewMessage(outgoing=True,pattern='.stop'))
async def stop(event):
    global hunt
    hunt = False


bot.start()
bot.run_until_disconnected()
### Host it on VPS or Locally

```sh
git clone https://github.com/dishapatel010/SnapchatStoriesBot
cd SnapchatStoriesBot
virtualenv -p /usr/bin/python3 venv
. ./venv/bin/activate
pip install -r requirements.txt
python3 -m bot
```
## Contact

[![Telegram Channel](https://img.shields.io/static/v1?label=Join&message=Telegram%20Channel&color=blueviolet&style=for-the-badge&logo=telegram&logoColor=violet)](https://telegram.dog/nexiuo)
