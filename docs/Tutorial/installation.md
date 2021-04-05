!!! warning "Read Before Starting"
    If you do not have any experience with Python, JavaScript, or Lua, it is recommended that you learn the basic foundation of one of those languages.
    
### Let's begin!

First off, we need to require the module and create a bot client. This is done differently in each language, so make sure to select the correct one below.

=== "Python"

    ``` py
    import discord
    client = discord.Client()
    ```

=== "JavaScript"

    ``` js
    const Discord = require('discord.js');
    const client = new Discord.Client();
    ```
    
=== "Lua"

    ``` lua
    local discordia = require('discordia')
    local client = discordia.Client()
    ```
    
Great! We've completed the first steps toward creating our very own Discord bot. Now, let's move on to [**events**](https://r0bl0x10501050.github.io/Making-Discord-Bots/Tutorial/events/).
