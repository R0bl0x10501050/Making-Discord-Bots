# ENVs

To use an env, you need to create a new file called ".env". In your env file, put the following:

=== "Env"

    ``` env
    TOKEN=PutTokenHere
    ```

Now, make sure to change your bot code! 

=== "Python"

    ``` py
    import discord
    import os
    client = discord.Client()

    @client.event
    async def on_ready():
        print('We have logged in as {0.user}'.format(client))

    @client.event
    async def on_message(message):
        if message.content == '!ping':
            await message.channel.send('Pong!')

    client.run(os.getenv("TOKEN"))
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

    client.login(process.env.TOKEN);
    ```
    
=== "Lua"

    ``` lua
    local discordia = require('discordia')
    local os = require('os')
    local client = discordia.Client()

    client:on('ready', function()
        print('Logged in as '.. client.user.username)
    end)

    client:on('messageCreate', function(message)
        if message.content == '!ping' then
            message.channel:send('Pong!')
        end
    end)

    client:run(os.getenv("TOKEN"))
    ```
    
And you're done! Have fun experimenting with Discord bots!

Have a bot you want to others to use? Join our [discord server](https://discord.gg/FEdAG2Kh9n) and submit your bot in `#bot-submissions`.
