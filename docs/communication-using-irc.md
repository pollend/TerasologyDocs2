
## Using our chat systems including IRC

IRC and other chat services like Slack and Discord can be a bit strange if you've never used anything like them before. Somewhere in between email and instant messaging the most important tool is patience :-)

Other live chat tools like Slack and Discord are becoming popular as well, and for our purposes are roughly used the same, yet they have nicer and newer features. You can join our Discord using this invite: https://discord.gg/4uKbB8J

Many users connect and let themselves idle in a *channel* like ours at `#terasology` on the [Freenode IRC network](https://freenode.net) - that doesn't mean they're watching the screen for new messages every moment. Please do not feel like people are ignoring you if you do not get a response right away as it may take a few hours before somebody looks for messages.
 
Ultimately the forum is better for guaranteed response if needed. Discord has nice chat history regardless of whether a person was logged in at the time or not.

You can join via webchat in a browser at https://webchat.freenode.net - just enter your desired nickname and `#terasology` for the channel to join.

### IRC User setup

If you want a more serious setup with IRC you need a dedicated client and to properly register an account.

* Pick a client - loads of these available, even as browser plugins for Firefox and Chrome
* Connect to chat.freenode.net - see http://freenode.net/kb/answer/chat for more details
* IRC generally dumps you in a system channel and expects you to use slash commands or menus to get stuff done 
  * Make sure any options in your client are set with your right name, nick, desired starting channel (#terasology), etc
  * You can set / change your nick by simply entering `/nick [mynick]`
  * If you want to safeguard your nickname / account register it by entering: `/msg nickserv register [password] [email]`
  * This will send you an email with a verification command to enter to verify your account
  * To then re-identify yourself to the server on each login you may have to enter a command like `/msg nickserv identify [password]` - most clients will allow you to automatically issue that on startup
* For additional help enter `/msg nickserv help`

## GooeyJr and gooey-bridge

GooeyJr is our friendly local IRC bot, the next generation of our previous IRC bot [Gooey](https://github.com/movingblocks/gooey). Lives at https://github.com/MovingBlocks/GooeyJr and is based on [Hubot](https://hubot.github.com)
 
For help with GooeyJr simply enter `GooeyJr help` in `#terasology` on Freenode, or even open a private message with the bot and use plain `help` to interact more quietly.

We use [matterbridge](https://github.com/42wim/matterbridge) to link IRC, Slack, and Discord, so messages will bridge from one service to another. This is limited to our general channels at the moment but may be expanded.

_Note:_ If you have a Slack account with an empty display name your **OS username** may end up attached to your bridged messages. And if you keep spaces in your display name your messages may fail to bridge entirely with only a `@` showing. Avatars might end up looking different, but if your display name equals your account name that helps matterbridge sync you better.

## See also

* Tutorial & terms: http://www.irchelp.org/irchelp/irctutorial.html
