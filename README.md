## LibreGroupHelp

Open-Source re-creation of telegram group manager Group Help in NodeJS based on [node-telegram-api](https://github.com/yagop/node-telegram-bot-api).

An official instance of bot is running on [@LibreGroupHelpBot](https://t.me/LibreGroupHelpBot)

## Installation:

```bash
npm install
```

Set your bot token on config.js, look at [config documentation](https://github.com/Sp3rick/GroupHelp/blob/main/CONFIG_DOCUMENTATION.md).

Run with:
```bash
node index.js
```

Installation trubleshooting:

if you have problems with node-telegram-bot-api installation try this command url based:
```bash
npm i https://github.com/yagop/node-telegram-bot-api
```

and if needed install other packages manually:
```bash
npm i chrono-node
```

## Contribute

Useful links to contribute:
[documentation.md](https://github.com/Sp3rick/GroupHelp/blob/main/documentation.md).
[Create a plugin](https://github.com/Sp3rick/GroupHelp/blob/main/plugins.md).


## Updating
To update the bot you need to backup ./database folder and ./config.json only, then repeat installation process and paste there the old database and config.json, you may need to add some config.json parameters manually


## Our TODO List:

-short term:

    allow to edit single user perms
    commands help panel

-medium term:

    allow on /perms to change user perms and roles, +add it in a button for /info or when a role is set (/free /mod etc..), +ask double confirm to give an user the "settings" and "roles" permission
    support for anonymous admins
    allow to customize /staff allowing to set roles to hide
    create a privacy setting where users can ask to esclude themself from tagResolver and replace his's first name in database with "Anonymous"
    allow to disable tagResolver log on group settings
    allow to mute only media, or specific media type or extras
    once bot will be declared ready to use, add code versioning system to update database when user update it
    create a privacy option to allow a user deleting his data from the bot
    custom roles
    optimize database.get, .update and .save to store in temporal array most used users
    implement time zone setting +implement it in /info

-long  term:

    add log channel
    compress chats data stored on database
    support all group help functions and more (+anti-sheduled messages[msg.is_from_offline], )
    allow bot clone bot when user give a token
    add optionally an userbot (when active implement in tagResolver.js)

-other things:

    implement direct private settings with /*settings
    add a /commands command to help user to know bot commands, admin commands, and custom-group commands if avaiable
    a check system to drop wrong formatted cb.data and user.waitingReplyType
    allow to see perms calculation trough user perms, then roles by priority, then base group perms, going from left to right (or opposite)
    add something to allow a group admin to identify all users with additional bot perms
    ?add an automatic leveling system for admins? (maybe?)
    add photo preview-mode in MessageMaker.js
    allow to warn only usersIds who exhist on telegram, it can be checked if applyng a restriction returns true
    add config to allow/disallow adding bot from non-admin users
    ?identify reply_parameters and add everytime allow_sending_without_reply? (GHBot.js)


## Known possible bugs:
-sometimes db.chats.update in plugins may be not used at all because you can still edit the global object cause to reference, not using it may cause some issue. +if global reference get cleared too early code may try to access and inexistent variable

-cleanHTML() may be not applyed in some text where it should, and nothing assure that it's 100% able to clean everything needed for telegram api

-if you add a new permission on userPerms object, every userPerms object should be updated adding that, otherwise this may cause incorrect result in sumUserPerms

-in some unkown cases you may get stuck in exceptions menu and SafeGram.js will block any user request due too high accumulated volume of something pending


## Ask a question

If you have any questions about LibreGroupHelp, feel free to open an issue or ask directly in our telegram group - [@LGHChat](https://t.me/LGHChat).