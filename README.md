# DiscordWebhook-GMS2.3Beta
 GameMaker Studio 2.3Beta extension for executing Discord webhooks.
Build on IDE v2.2.5.481 <br>
[GMS 2.2 version](https://github.com/DmitrijVC/DiscordWebhook-GMS2) <br>
[Marketplace]()

This asset was made in mind of simpler executing of Discord webhooks and it is script and object based. <br>
It is holding each webhook in an object named *obj_dcw*. <br>
There is also an example of usage as an object in group *Demo* named *obj_DiscordWebhooksDEMO*. <br>
<br>

### Importing
You can open the project *(DiscordWebhooks_2B.yyp)* or just import ready package *(com.Vulco.DiscordWebhook2_3Beta.yymps)*. <br>
All necessary things are placed in groups named *Discord Webhook* and the demo ones in groups *Demo*. <br>
<br>

### Usage
If you imported everything without errors you shold now have access to scripts like:

  - discord_webhook

There is also object with name *obj_dcw*, it holds all data about the webhook. <br>
Example of Discord webhook: <br>
`https://canary.discordapp.com/api/webhooks/<ID>/<TOKEN>` <br>
<br>


**discord_webhook(arg1, arg2)** [script] <br>
Creates a new webhook object and returns it's unique ID, which you need to edit or execute the webhook. <br>
arg1: ID of the webhook <br> 
arg2: TOKEN of the webhook <br> 
returns: Webhook object ID <br>
<br>


**execute()** [method] <br>
Execute the webhook. <br>
<br>

**destroy()** [method] <br>
Destroy the webhook object. <br>
<br>

**change_urlID(arg1)** [method] <br>
Changes webhook ID <br>
arg1: ID of the webhook <br> 
<br>

**change_urlToken(arg1, arg2)** [method] <br>
Changes webhook TOKEN <br>
arg1: TOKEN of the webhook <br> 
<br>


**Webhook object's attributes** <br>
Required: 🔹 <br>
Can use macro dcw_noone: 🔸 <br><br>
­ ­ • url *- full Discord webhook url* (string) <br>
­ ­ • url_id *- id of the webhook* (string/int) 🔹 <br>
­ ­ • url_token *- token of the webhook* (string) 🔹 <br>
  
­ ­ • content *- content of the message* (string) 🔹🔸 <br>
­ ­ • username *- webhook username* (string) <br>
­ ­ • avatar_url *- webhook avatar url* (string) <br>
  
­ ­ • embed_use *- enable or disable embed* (bool) <br>
­ ­ ­ ­ • embed_title *- title of the embed* (string) 🔸 <br>
­ ­ ­ ­ • embed_description *- description of the embed* (string) 🔸 <br>
­ ­ ­ ­ • embed_url *- url of the embed* (string) <br>
­ ­ ­ ­ • embed_color *- colour of the embed* (int) <br>
  
­ ­ ­ ­ • embed_author_name *- name of the author* (string) 🔸 <br>
­ ­ ­ ­ ­ ­ • embed_author_url *- url of the author* (string) <br>
­ ­ ­ ­ ­ ­ • embed_author_iconUrl *- icon url* (string) <br>
  
­ ­ ­ ­ • embed_image_url *- url of an embed image* (string) <br>
­ ­ ­ ­ ­ ­ • embed_image_width *- width* (int) <br>
­ ­ ­ ­ ­ ­ • embed_image_height *- height* (int) <br>
  
­ ­ ­ ­ • embed_footer_text *- content of the footer* (string) 🔸 <br>
­ ­ ­ ­ ­ ­ • embed_footer_iconUrl *- icon of the footer* (string) <br>
  
­ ­ ­ ­ • embed_thumbnail_url *- image url of the thumbnail* (string) <br>
­ ­ ­ ­ ­ ­ • embed_thumbnail_width *- width* (int) <br>
­ ­ ­ ­ ­ ­ • embed_thumbnail_height *- height* (int) <br>
  
­ ­ ­ ­ • embed_video_url  *- video url* (string) <br>
­ ­ ­ ­ ­ ­ • embed_video_width *- width* (int) <br>
­ ­ ­ ­ ­ ­ • embed_video_height *- height* (int) <br>
  
­ ­ ­ ­ • embed_provider_name *- name of the provider* (string) <br>
­ ­ ­ ­ ­ ­ • embed_provider_url *- url of the provider* (string) <br>
<br>

### Example
```cpp
webhook1 = discord_webhook(730000000000000001, "PYS*************************************************************7QH8");

webhook1.content = dcw_noone;
webhook1.username = "Vulco's Webhook";
webhook1.avatar_url = "https://i.imgur.com/YlKAVA5.png";

webhook1.embed_use = true;
webhook1.embed_title = "That's my own title";
webhook1.embed_description = string_hash_to_newline("And that's a __*description*__#in multiple lines!!");
webhook1.embed_color = 0xb52828;

webhook1.embed_author_name = "Author - FssAy";
webhook1.embed_author_iconUrl = "https://cdn.discordapp.com/avatars/701563061735129138/8dea766fcfd4cb02809ad59032d4eaa0.png";

webhook1.embed_footer_text = "Made in GameMaker Studio 2.3 Beta";
webhook1.embed_footer_iconUrl = "https://image.prntscr.com/image/9AS6SYxWSdS_cBt47VDvlw.png";

webhook1.embed_thumbnail_url = "https://i.imgur.com/YlKAVA5.png";

webhook1.execute();
```
<br>
