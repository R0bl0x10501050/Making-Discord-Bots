!!! question "What Are Events?"
    **Events** are connections between two systems. In this case, the two systems are Discord and your bot. For example, when you start typing in a channel, Discord will notify your bot that someone is typing, and who it is. Don't understand? Join our [discord server](https://discord.gg/FEdAG2Kh9n)!

We'll first want to create an **event listener** for when your bot logs in. This can help ensure that your bot is logged on and ready to go.

=== "Python"

    ``` py
    import discord
    client = discord.Client()

    @client.event
    async def on_ready():
        print('We have logged in as {0.user}'.format(client))
    ```
    
=== "JavaScript"

    ``` js
    const Discord = require('discord.js');
    const client = new Discord.Client();

    client.on('ready', () => {
        console.log(`Logged in as ${client.user.tag}!`);
    });
    ```
    
=== "Lua"

    ``` lua
    local discordia = require('discordia')
    local client = discordia.Client()

    client:on('ready', function()
        print('Logged in as '.. client.user.username)
    end)
    ```

Great! Our "ready" event listener is now set up. Let's move onto the fun part: listening for messages.

___

Listening for messages isn't much different than listening for the "ready" event.

=== "Python"

    ``` py
    import discord
    client = discord.Client()

    @client.event
    async def on_ready():
        print('We have logged in as {0.user}'.format(client))
    
    @client.event
    async def on_message(message):
        if message.content == '!ping':
            await message.channel.send('Pong!')
    ```
    
=== "JavaScript"

    ``` js
    const Discord = require('discord.js');
    const client = new Discord.Client();

    client.on('ready', () => {
        console.log(`Logged in as ${client.user.tag}!`);
    });
    
    client.on('message', msg => {
        if (msg.content === '!ping') {
            msg.channel.send('Pong!');
        }
    });
    ```
    
=== "Lua"

    ``` lua
    local discordia = require('discordia')
    local client = discordia.Client()

    client:on('ready', function()
        print('Logged in as '.. client.user.username)
    end)
    
    client:on('messageCreate', function(message)
        if message.content == '!ping' then
            message.channel:send('Pong!')
        end
    end)
    ```
    
And with that, our bot is almost ready to run. However, there is [one more crucial step](https://r0bl0x10501050.github.io/Making-Discord-Bots/Tutorial/login) to finishing a bot.
