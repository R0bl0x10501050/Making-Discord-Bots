We're almost done with our bot! However, we need to make the bot actually log in.

!!! info "How To Get Your Bot Token"
    To make our bot log in, we need a **token**. To get our bot token we first need to head over to the [Discord Developer page](https://discord.com/developers/applications). Once we're there, we need to create a new application. Then, headover to the "Bot" tab on the left and create a bot. Once we've created a bot, the center of the "Bot" page should have a "Copy" button. Click that, and you have your token!

Once we have our token, add a "run" function and include the token as the parameter.

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

    client.run('INSERT_TOKEN_HERE')
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
            msg.reply('Pong!');
        }
    });

    client.login('INSERT_TOKEN_HERE');
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

    client:run('Bot INSERT_TOKEN_HERE')
    ```
    
Congrats! You've finished your first ever Discord bot! Run the program, invite the bot to your server, and you're all set!

!!! info "Being Secure"
    Don't want your private bot tokens out in the public? Don't worry, since envs, or environment variables, exist for this purpose. To learn how to use an env file, check out the [Advanced]() page.
