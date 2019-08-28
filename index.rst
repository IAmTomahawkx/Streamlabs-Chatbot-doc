.. Streamlabs Chatbot documentation master file, created by
   sphinx-quickstart on Tue Aug 27 22:59:33 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Streamlabs Chatbot documentation!
============================================

.. toctree::
   :maxdepth: 6
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`


features
========

Console
--------
On the console you will see all the incoming chat messages and the viewer list.
In case you dislike seeing who’s watching you can simply click the small button left of the viewer list to dock it to the side.
Aside from this at the top of the console you have access to Macro buttons which you can bind commands to.
Further in the document this will be explained in more detail.


Dashboard
---------
| In order to access the full capability of the Dashboard you need to have your own Twitch account connected under Connections -> Twitch Streamer.
| This should be done if you followed the entire setup guide in the beginning.

This is where you will be able to change your Title & Game, run commercials if you’re partnered with Twitch, have the bot automatically host streams of your choosing and where the bot will track news Followers, Subscribers, Raiders, Hosts and GameWisp Subscribers.
We also have Raid Assist which is a system which allows you to reward viewers for joining you on a raid.
The Session Event View which is located at the bottom of the Dashboard will have to be manually cleared before each stream by right clicking and Clearing the data. Otherwise new Hosts, Raids, Subs/Resubs won't be logged if they're done by the same person.

+------------------------+-------------------------------+--------------------------------------------------------+
|          Usage         | Example                       | Response                                               |
+========================+===============================+========================================================+
| !Status (message)      | !Status [24h] Charity Stream! | {user} -> Title has been updated: [24h] Charity Stream!|
+------------------------+-------------------------------+--------------------------------------------------------+
| !Game (message)        | !Game The Last of Us          | {user} --> Game has been updated: The Last of Us       |
+------------------------+-------------------------------+--------------------------------------------------------+
| !StartHost             | !StartHost                    | {user} --> Started Automated Hosting!                  |
+------------------------+-------------------------------+--------------------------------------------------------+
| !StopHost              | !StopHost                     | {user} --> Stopped Automated Hosting!                  |
+------------------------+-------------------------------+--------------------------------------------------------+


Commands
--------
This is where you would start off if you want to create Commands. There are $parameters that you can use in the commands to achieve various result. More information on these parameters can be found on page XYZ.
$Parameters & Permission levels can be found further in to the documentation.

There is also support for Command Grouping any group starting with [GAME] will only work when you're actually playing the game which is defined behind the tag

ex: [GAME] Pokemon Go

+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|          Usage                                     | Example                                                | Response                                                     |
+====================================================+========================================================+==============================================================+
| !Command Add (command) (permlvl) (response)        | !Command Add !Cookie +r All your cookies belong to me! |{user} --> Successfully added !Cookie. Permission:            |
|                                                    |                                                        |Regular - Message: All your cookies belong to me!             |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
| !Command Edit (command) (permlvl) and/or (response)| !Command Edit !Cookie +a /me ate $count cookies!       |{user} --> Successfully edited !Cookie.                       |
|                                                    |                                                        |Permission: Everyone. Message: /me ate $count cookies!        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
| !Command Remove (command)                          | !Command Remove !Cookie                                | {user} --> Successfully removed !Cookie.                     |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
| !Command Count (command) (num)                     | !Command Count !cookie 10                              |{user} --> Successfully set the count for !cookie to 10       |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Command Usage (command)                            | !Command Usage !cookie SC                              |{user} --> Successfully set the usage of $command to $value.  |
|(usage ex: SC,SW,SB,DC,DW,DB,CB,WB,A)               |                                                        |                                                              |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Enable (command) (true/false)                      |!Enable !cookie true                                    |{user} --> Succesfully enabled !Cookie                        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Command Cooldown (command) (minutes)               |!Command Cooldown !cookie 2                             |{user} --> Successfully set the cooldown of !cookie to 2.     |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Command UserCooldown (command) (minutes)           |!Command Cooldown !cookie 5                             |{user} --> Successfully set the user cooldown of !cookie to 5 |
|                                                    |                                                        |Regular - Message: All your cookies belong to me!             |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+

--------

Sharing Commands
 | If you wish to share commands with your fellow streamer you can export them as .abcom (Streamlabs Chatbot Command) or .abcomg (Streamlabs Chatbot Command Group) by right clicking on a command. You have two options Export Command to export the single command or Export Group to Export all commands in that specific Group.

--------

Importing Commands
 | Importing a script is simple. Simply click the Import Button in the Command Tab, Navigate to the Zip File and Open it. Afterwards the bot will import the script for you and reload your scripts so it's ready to go.


Timers
------

This is where you will create your own Timers. These are messages that the bot will automatically post into chat after an interval of X minutes. The interval is completely based on the Setting at the top.

All the timers will follow this same interval so this means the bot will post the first timer after the interval passes. Then it will start timing again, once the interval passes again it will post the second timer and so on eventually going through all of them and then starting back at the top.

There is also support for Timer Grouping any group starting with [GAME] will only trigger when you're actually playing the game which is defined behind the tag
ex: [GAME] Pokemon Go


+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|          Usage                                     | Example                                                | Response                                                     |
+====================================================+========================================================+==============================================================+
|!Timer Add (name) (response)                        |!Timer Add !Meow /me meows at $randusername             |{user} --> Successfully added !meow. Message:                 |
|                                                    |                                                        |/me meows at $randusername                                    |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Timer Edit (name) (response)                       |!Timer Edit !Meow /me growls at $randusername           |{user} --> Successfully edited !Meow. Message: /me            |
|                                                    |                                                        |growls at $randusername                                       |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Timer Remove (name)                                |!Timer Remove !Meow                                     |{user} --> Successfully removed !Meow.                        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Activate (name) (true/false)                       |!Activate !Meow false                                   |{user} --> Succesfully de-activated !Cookie                   |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+


Quotes
------

This is where things you’ve said on stream can be stored. You can change the permission on who can request a random quote and who can add them for you through chat.

You can also set the Cooldown and the Date Format. Every quote that gets added will automatically contain the Game & Date when the quote was created. So whenever someone calls upon the random quote they’ll see when it happened and what you were playing at the time.

+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|          Usage                                     | Example                                                | Response                                                     |
+====================================================+========================================================+==============================================================+
|!Quote Add (text)                                   |!Quote Add "I am a cat!" - AnkhHeart                    |{user} --> Succesfully added Quote #0: "I am a cat!"          |
|                                                    |                                                        |– AnkhHeart [Thief] [01/01/2015]                              |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Quote Edit (id) (text)                             |!Quote Edit 0 "I am not a cat!" –                       |{user} --> Successfully edited Quote #0: "I am not a cat!"    |
|                                                    |AnkhHeart [Thief] [02/01/2015]                          |– AnkhHeart [Thief] [02/01/2015]                              |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Quote Remove (id)                                  |!Quote Remove 0                                         |{user} --> Successfully deleted Quote #0                      |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Quote                                              |!Quote                                                  |Quote #2: "Duct tape solves all problems!" - AnkhHeart        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Quote (id)                                         |!Quote 0                                                |Quote #0: "I am not a cat!" - AnkhHeart                       |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+

Extra Quote
-----------

Using the Extra Quotes you can create your own version of the Quote System to store things that aren’t specifically quotes. You can change the command, decide whether you want the Game & Date to show or not, change the Permissions and Response.

The underlying chat commands function the same way except if you do change the command you will also have to adjust the commands. By default this is !Gif if you change it to !Pun then you will have to use the commands starting with !Pun instead of !Gif.

+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|          Usage                                     | Example                                                | Response                                                     |
+====================================================+========================================================+==============================================================+
|!Gif Add (text)                                     |!Gif Add http://tinyurl.com/randomGif.gif               |{user} --> Succesfully added Gif #0:                          |
|                                                    |                                                        |http://tinyurl.com/randomGif.gif                              |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Gif Edit (id) (text)                               |!Gif Edit 0 http://tinyurl.com/randomGif2.gif           |{user} --> Successfully edited Gif #0:                        |
|                                                    |                                                        |http://tinyurl.com/randomGif2.gif                             |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Gif Remove (id)                                    |!Gif Remove 0                                           |{user} --> Successfully deleted Gif #0                        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Gif                                                |!Gif                                                    |Gif #2: http://randomURL.com/randomGif15.gif                  |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Gif (id)                                           |!Gif 0                                                  |Gif #0: http://randomURL.com/randomGif2.gif                   |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+

Counter
-------

You can use the Counter to create a Death Counter, Hug Counter, Cookie Counter, etc.. It’s used to count anything. You can change the settings to your liking just be sure to keep a # in the Msg Template since this will be replaced by the number.

In case you want to use the Counter but do not want to Capture the Display Area you can make use of a Death.txt file that is Located in the Bot’s Install Directory -> Services -> Twitch -> Files Folder.

This file will be generated when you’ve added your first death. If you want to manually create this file then simply type !death 0 in chat. This will create the file with 0 Deaths inside. Do mind though if you changed the Command to something else you will have to use that instead.

+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|          Usage                                     | Example                                                | Response                                                     |
+====================================================+========================================================+==============================================================+
|!Death +                                            |!Death +                                                |[Increased] Deaths: 124                                       |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Death -                                            |!Death -                                                |[Decreased] Deaths: 124                                       |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Death (num)                                        |!Death 10                                               |[Set] Deaths: 10                                              |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+
|!Death                                              |!Death                                                  |Deaths: 10                                                    |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------+

Giveaway
--------

This is where you will be able to start Give Aways. You can either have people join the Give Away for free or have them pay a fee to enter or have them pay per ticket using in Channel Currency.

On the left side you will find all the people that are entered in the Give Away and how many tickets they possess. At the bottom of the window you will see all the messages posted by the Winner when one has been picked. That way you’ll know if the user is active in case chat is moving really quickly.

+-----------------------------------------------------------------------+--------------------------------------------------------+---------------------------------------------------------------+
|          Usage                                                        | Example                                                |Description                                                    |
+=======================================================================+========================================================+===============================================================+
|(see below)                                                            |(see below)                                             |This starts a giveaway through chat with your own settings     |
+-----------------------------------------------------------------------+--------------------------------------------------------+---------------------------------------------------------------+
|(see below)                                                            |(see below)                                             |starts a very simple give away without tickets and entry costs |
+-----------------------------------------------------------------------+--------------------------------------------------------+---------------------------------------------------------------+
|!Giveaway Close                                                        |!Giveaway Close                                         |Prevents anyone from entering past this point                  |
+-----------------------------------------------------------------------+--------------------------------------------------------+---------------------------------------------------------------+
|!Giveaway Winner                                                       |!Giveaway Winner                                        |Randomly picks the winner for the Give Away                    |
+-----------------------------------------------------------------------+--------------------------------------------------------+---------------------------------------------------------------+

Sound Files
-----------

The Sound Files tab allows you to add sounds to the bot which you can attach to notifications and commands. From within this tab you are able to control the Volume and Votes. The votes option only applies to commands as it determines how many times a command has to be used before the sound goes off.

Currency
--------

If the currency System is enabled everyone in your chat will start earning points based on your settings. These can be spent using the various other Systems in the bot such as Give Aways, SFX, Bet/Vote and enter Minigames.

The bot also supports Streamlabs currency. For this you need to connect Streamlabs and enable this functionality in your currency settings inside of the bot.

You can create up to four Ranking Trees: One for Viewers, Subscribers, Mods and GameWisp Subscribers. Ranks are only assigned whenever the bot pays out points or when you use !points add +viewers 1 for example.

There is also room for customizing your own Payout amounts and intervals. This way you have full control over how many points people can accumulate in your stream.

If the Offline Payout amount is set to 0 the bot will not pay out any points with the stream is offline. Also replace !points with your own custom currency command.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Points Add (name) (amount)                         |!Points Add AnkhHeart 10000                             |{user} --> Successfully given AnkhHeart 10000 Points                           |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Points Remove (name) (amount)                      |!Points Remove AnkhHeart 1234                           |{user} --> Successfully removed 1234 Points from AnkhHeart                     |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Points Add +Viewers/+active (amount)               |!Points Add +viewers 100                                |{user} --> Done giving 100 Points to everyone in chat                          |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Points Remove +Viewers/+active (amount)            |!Points Remove +viewers 100                             |{user} --> Done removing 100 Points from everyone in chat                      |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Points                                             |!Points                                                 |AnkhHeart [Ninja Kitty] - Hours: 13 - Points: 1337                             |  EVERYONE    |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Transfer                                           |!Transfer AnkhHeart MohammedBaraax1                     |{user} --> Successfully transferred currency from AnkhHeart to MohammedBaraax1 |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Betting
-------

Using the Betting System you can open up the ability for Viewers to bet on the outcome of situations. These options can be saved into a present and loaded later in case you are playing the same game again.

If you wish to pick a winning option simply right click on the option and Pick it as the Winner. In case there are multiple correct Options this can be done for each of them.


+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Description                                                                   | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Bet (id) (amount)                                  |!Bet 0 1000                                             |[No response to prevent chat spam from the bot]                                |  EVERYONE    |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!betting start (see below)                          |!Betting Start (see below)                              |This starts a custom betting session with custom settings                      |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Betting Start (see below)                          |!Points Start (see below)                               |This starts a custom betting session that will use the settings                |  EDITOR      |
|                                                    |                                                        | that have been set in the UI                                                  |              |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Betting Stop                                       |!Betting Stop                                           |Prevents anyone from betting once used                                         |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Betting Abort                                      |!Betting Abort                                          |Cancels betting entirely and refunds anyone that has bet                       |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Betting Winner (id)                                |!Betting Winner 0                                       |Picks the winning option and pay out points to everyone that bet on it         |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Poll
----

The Poll System allows you to start a poll in your channel and have your viewers vote. In case you want people to spend points for each vote they cast then you can enable this by checking Allow Multi Voting and increase the limit.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Description                                                                   | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Vote (id)                                          |!Vote 1                                                 |[No response to prevent chat spam from the bot]                                |  EVERYONE    |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Poll start (see below)                             |!Poll Start (see below)                                 |This starts a custom poll with your own settings (overwrites UI settings)      |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Poll Start (see below)                             |!poll start (see below)                                 |This starts a custom poll that will use the settings                           |  EDITOR      |
|                                                    |                                                        |that have been set in the UI                                                   |              |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Poll Stop                                          |!Poll Stop                                              |Ends the poll and posts the result in chat                                     |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Minigames
---------

Heist
+++++

The Group Minigame allows you to create your own Minigame. You can start the customization by determining the Command that will be used, what the cooldown is, how many users have to enter before it starts, the Max amount someone can invest and who can Join.

Aside from all those options you can set the Probability for each usergroup. This determines how much chance people within that usergroup have to survive. The Payout can also be set that way you can choose how much someone gets ontop of the amount they invested in the minigame.

Finally you can fully customize all the messages that the bot will be posting in chat depending on the situation and how well/bad things are going for the ones that have joined. So if you wanted you could turn it into something completely different and not use the default Heist preset.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Heist (amount)                                     |!Heist 123                                              |{user} is trying to get a team together in order to hit the nearest bank.      |  JOIN        |
|                                                    |                                                        | - Everyone can Join!- In order to join type !Heist (amount).                  |  PERMISSION  |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Duel
++++

The Duel minigame allows viewers to challenge each other to a battle. The bot will process a secretive battle in the background, the winner will receive twice the cost. The loser will get nothing.

Aside from this both the challenger and challenged will go on cooldown once their fight concludes and can no longer challenge or be challenged till their cooldown expires.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!challenge (name)                                   |!Challenge ankhheart                                    |{user} has challenged {target} to a fight! Type !challenge {user}              |  JOIN        |
|                                                    |                                                        |to accept the challenge!                                                       |  PERMISSION  |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Free-For-All
++++++++++++

In the Free for All minigame multiple viewers can face off against one another. You can determine how many people end up surviving. The more people join the larger the prize pool becomes and the winner walks away with the pot. In more than one person can survive then it gets split amongst the survivors.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!ffa                                                |!ffa                                                    |The arena is now open! Type !ffa to join!                                      |  JOIN        |
|                                                    |                                                        |                                                                               |  PERMISSION  |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Boss Battle
+++++++++++

This allows you to create custom bosses for your viewers to fight based on how many people join. The difficulty / loot is completely up to you do mind that balancing it fairly is also your responsibility.

The Basics:
 | Balancing of the minigame is completely up to you so let's go down some of the basic concepts so you know how it functions in the background. That way you can determine what values would be best.
 | 1) Players sign up for the battle and get a Stat sheet assigned based on their permission
 | 2) Boss gets picked based on the group size (Between Min – Max Entries)
 | 3) The fight starts against the boss
 | 4) Damage Calculation: (User Attack – Target Defense) ex: 10 att – 5 def = 5 dmg that the target will receive
 | 5) Attack order: The boss has to be attacked 3 times before it counters the last attacker. So let's say we have a group with Ankh, Momo and Gooru and Ankh attacks first and then Momo and then Gooru. After Gooru finishes his attack he would get countered by the boss and be the only person to receive damage. Now prior to every attack phase taking place the order of people attacking will be shuffled so it's not always the same person getting countered.
 | 6) Make sure to keep the Boss's Defense lower than Player's Attack at all times so they at least have a chance to beat him
 | 7) Balance the health based on the Min – Max Entries for this you will have to do a bit of math yourself based on the prior information given such as: Dmg Calculation and Attack Order
 | 8) The Max Defense a player/boss can have is half their attack if this is higher than it will be capped out during calculation at 50%
 | 9) Loot will get distributed evenly amongst all of the survivors at the end. In case no one survives then there is no loot to be distributed

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!boss                                               |!boss                                                   |{user} is trying to get a group of adventurers together to fight a boss!       |  JOIN        |
|                                                    |                                                        |Type !boss to join him!                                                        |  PERMISSION  |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Events
------

The Event System will allow the bot to automatically Greet/Shoutout the person of your choice and play a SFX if you wish. The system consists of two modes Join events and Speak events.

Join Events will perform its action when the person of your choice joins the channel. Then it will post its message and/or play its SFX.

Speak Events will perform its action when the person of your choice speaks in your channel for the first time. Then it will post its message and/or play its SFX.

In order for the bot to re-execute the events it has to be restarted. So the best thing is to restart it before a cast.

Song Requests
-------------

The Song Request System allow you to create your own youtube playlist through the bot have them play whenever you want. Aside from that your viewers can request songs and spend currency to do so.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Songrequest (url/token)                            |!Songrequest TY9cSlOhqTk                                |{user} --> The song Amv - [MEP] Ѕο Lοng Ѕеntimеnt has been added to the queue  |REQUEST PERM  |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Skip                                               |!Skip                                                   |{user} --> Your vote to skip has been successfully registered!                 |  SKIP PERM   |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Veto                                               |!Veto                                                   |Amv - [MEP] Ѕο Lοng Ѕеntimеnt 720p has been successfully skipped!              |VETO PERM     |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Songblacklist add (id)                             |!songblacklist add dQw4w9WgXcQ                          |{user} --> dQw4w9WgXcQ has been successfully Blacklisted!                      |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Songblacklist remove (id)                          |!songblacklist remove dQw4w9WgXcQ                       |{user} --> dQw4w9WgXcQ has been successfully Un-Blacklisted!                   |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Wrongsong                                          |!Wrongsong                                              |{user}, Successfully removed the last song you requested.                      |  EVERYONE    |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Songlist                                           |!Songlist                                               |[Create this yourself and point it to                                          |  EVERYONE    |
|                                                    |                                                        |https://streamlabs.com/<your_name>#/chatbot/songlist]                          |              |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Volume (number)                                    |!Volume 50                                              |{user}, Volume set to 50                                                       |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Queue
-----

You can setup a Game Queue using this which allows your viewers to sign up to join you in a multiplayer game. You can have them spend currency to enter and you can even set it to Sub only in case you only want Subscribers to be able to sign up.

+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                      | Permission   |
+====================================================+========================================================+===============================================================================+==============+
|!Join <note>                                        |!Join AnkhHeart#4798                                    |[None unless enabled under Settings -> Localization]                           |EVERYONE      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Queue Open <game>                                  |!Queue Open Warframe                                    |A queue has opened up for: Warframe - Cost: 0 points -                         |  EDITOR      |
|                                                    |                                                        |Type !join (optional:Note) to join!                                            |              |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Queue Close                                        |!Queue Close                                            |The queue has been closed! You can no longer enter!                            |EDITOR        |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Queue Clear                                        |!Queue Clear                                            |The Queue has been cleared!                                                    |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Queue Pick <number>                                |!Queue Pick 3                                           |Next up: AnkhHeart, Castorr91, Must13                                          |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Queue Random <number>                              |!Queue Random 3                                         |Next up: FurRiffic, WellBrained, Ocgineer                                      |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+
|!Leave                                              |!Leave                                                  |AnkhHeart has left the queue.                                                  |  EVERYONE    |
+----------------------------------------------------+--------------------------------------------------------+-------------------------------------------------------------------------------+--------------+

Notifications
-------------

You will find various in Chat Notifications here ranging from Follower, Host, Subscriber Notifications to GameWisp Notifications. You can customize each of these to your liking.

The Follow, Subscriber, Host & Streamlabs notifications require you to have your Streamlabs account connected.

The Cheer Notifications require you to have your Streamer Account connected.

The Extra Life Notifications require you to connect your Extra Life Parcipant ID.

The GameWisp Subscriber Notification is only available if you have connected your Gamewisp Account.

Mod Tools
---------

Using the Mod Tools you can have the bot punish viewers that post Links without permission, Spam Caps/Symbols or very offensive words/sentences.

Each of these can be fully customized. When it comes to Link Protection you can exempt certain websites from being punished.

For the Word/Sentence Blacklist you can also make use wildcards such as \* or ?. More information about Wildcards can be found on the internet ex: https://en.wikipedia.org/wiki/Wildcard_character

Discord
-------
The Discord tab will allow you to activate specific functionality to work in Discord in regards to Timers, automatically assigning a role to everyone and even announcing when you go live.

More on Discord can be seen in the _`FAQ`

Users
-----

In the Users tab you can see every user’s id, name, whether they’re an editor, external sub or regular. What they’ve been blacklisted from, how many times they’ve raided you and when they were last in your channel. From here you are also able to assign the Editor status to users whom you trust. They are then able to use Editor based chat commands to add, edit, remove commands, currency, start giveaways, etc...

Settings
========

General
-------

In the General Settings you will find some basic functionality such as the delay between bot messages, Auto connecting all your accounts when you launch it, etc...

Aside from this you can also setup a !raider command that can be used by Mods to save out a list of users that have raided your channel. These users will also get added to the Data.xlsx file in your Cloud folder if you have set that up.

+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------------------------+--------------+
|          Usage                                     | Example                                                | Response                                                                       | Permission   |
+====================================================+========================================================+================================================================================+==============+
|!Reg Add/Remove (Name)                              |!Reg Add AnkhHeart / !Reg Remove AnkhHeart              |AnkhHeart has become a Regular! / AnkhHeart is no longer a Regular.             |EDITOR        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------------------------+--------------+
|!Sub Add/Remove (Name)                              |!Sub Add AnkhHeart / !Sub Remove AnkhHeart              |AnkhHeart has become a Subscriber! / AnkhHeart is no longer a subscriber        |  EDITOR      |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------------------------+--------------+
|!Blacklist Add/Remove (Name)                        |!Blacklist Add AnkhHeart / !Blacklist Remove AnkhHeart  |AnkhHeart has been Blacklisted! / AnkhHeart has been removed from the blacklist |EDITOR        |
+----------------------------------------------------+--------------------------------------------------------+--------------------------------------------------------------------------------+--------------+

Localization
------------
Within the Localization you have the ability to change any of the default responses though try to keep most of the $parameters unless you really don’t want them to be there.

Usage
-----
Within the Usage you can change where and how commands can be used. Whether it be Chat, Whispers or Discord or everywhere.
In the Core you can determine if users have to be in your Channel to use Whisper commands with the bot or not.

Macros
------
This is where you are able to setup Macros for the 7 buttons in the Console UI. It’s a simple way to setup a few buttons to automatically post commands / messages in chat for you when you click them.

Hotkeys
-------
Using the Hotkeys you can set up Global Hotkeys for various actions within the bot such as Pausing a song, adding it to your playlist, skipping, increasing the volume,... Aside from this you’re also able to setup Hotkeys for the previously Mentioned Macros so you don’t have to click the buttons yourself. You can just hit your hotkey and it will execute them for you. Also don't forget to click Apply at the bottom to save your Hotkeys

Style
-----
In case you’re unhappy with the colours of Streamlabs Chatbot’s UI then this is where you would go. You can change every single colour here though you have to set the Style to Custom. Once you’re done with your changes and you like the result simply click on Save Custom Style and it will be saved.

Changelogs
----------
This is where you will be to read up on the Changelogs in case you didn't read them prior to updating to a newer version.

Misc
====

Permission Levels
-----------------
basic permissions

+-----------------+---------------------+
|  Usage          | Permission          |
+=================+=====================+
| +a              | Everyone            |
+-----------------+---------------------+
| +r              | Regular             |
+-----------------+---------------------+
| +s              | Subscriber          |
+-----------------+---------------------+
| +gw             | GameWisp Subscriber |
+-----------------+---------------------+
| +m              | Moderator           |
+-----------------+---------------------+
| +e              | Editor              |
+-----------------+---------------------+

Special Permissions

+-----------------+---------------------------+--------------------------+
|  Usage          | example                   | Permission               |
+=================+===========================+==========================+
| +u(name)        |  +u(ankhheart)            | User Specific            |
+-----------------+---------------------------+--------------------------+
| +r(MinRank)     |  +r(Lion)                 | Minimum Rank             |
+-----------------+---------------------------+--------------------------+
| +p(MinPoints)   |  +p(1000)                 | Minimum Points           |
+-----------------+---------------------------+--------------------------+
| +h(MinHours)    |  +h(13)                   | Minimum Hours            |
+-----------------+---------------------------+--------------------------+

Usage Levels
------------

+-----------------+---------------------+
|  Usage          | Permission          |
+=================+=====================+
| SC              | Stream Chat         |
+-----------------+---------------------+
| SW              | Stream Whisper      |
+-----------------+---------------------+
| SB              | Stream Both         |
+-----------------+---------------------+
| DC              | Discord Chat        |
+-----------------+---------------------+
| DW              | Discord Whisper     |
+-----------------+---------------------+
| DB              | Discord Both        |
+-----------------+---------------------+
| CB              | Chat Both           |
+-----------------+---------------------+
| WB              | Whisper Whisper     |
+-----------------+---------------------+
| A               | A                   |
+-----------------+---------------------+

Parameters
----------

Basic Parameters
++++++++++++++++

+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+===========================+=============================================================================+===================================================+==================================+
| $desc(description)       |Special parameter that can be placed on the first line of a                                              | $desc(This command does an API call somewhere!)   | [whatever the api returns]       |
|                          |command to sync a custom description to the web                                                          | $readapi(https://randomapi.com/thing)             |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $userid                  |Displays the user’s id, in case of Twitch it’s the user’s name in lower case characters.                 | /me steals a cookie from $userid                  |Bot steals a cookie from          |
|                          |Make sure to use $userid when using $addpoints, $removepoints, $givepoints parameters.                   |                                                   |ankhheart                         |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $username                |Make use of this parameter when you just want to output a good looking version of their name to chat.    | /me steals a cookie from $username                |Bot steals a cookie from          |
|                          |                                                                                                         |                                                   |AnkhHeart                         |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $targetid                |Displays the target’s id, in case of Twitch it’s the target’s name in lower case characters.             |/me kicks $targetid in the face! |                 |Bot kicks ankhheart in the face!  |
|                          |Make sure to use $targetid when using $addpoints, $removepoints, $givepoints parameters.                 |!kick AnkhHeart                                    |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $touserid                |Displays the target’s or user’s id, in case of Twitch it’s the target’s or user’s name in lower case     |/me kicks $touserid in the face!                   |Bot kicks chair in the face! or   |
|                          |characters. Make sure to use $touserid when using $addpoints, $removepoints, $givepoints parameters.     |!kick Chair or !kick                               |Bot kicks ankhheart in the face   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $tousername              |Displays the target’s or user’s display name. Make use of this parameter when you just want to           |/me kicks $tousername in the face!                 |Bot kicks chair in the face! or   |
|                          |output a good looking version of their name to chat.                                                     |!kick Chair or !kick                               |Bot kicks ankhheart in the face   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $botname                 |Displays the bot’s name                                                                                  |Hello I am $botname | !name                        |Bot: Hello I am StreamlabsBot!    |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $randuserid              |Displays a random user that has spoken in chat recently. In case of Twitch it’s the random user’s name   |/me gives $randuserid a hug! | !hug                |Bot gives ankhheart a hug!        |
|                          |in lower case characters.                                                                                |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $randusername            |Displays a random user that has spoken in chat recently. Make use of this parameter when you just want   |/me gives $randusername a hug! | !hug              |Bot gives AnkhHeart a hug!        |
|                          |to output a good looking version of their name to chat.                                                  |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $msg                     |Displays the text after the command                                                                      |$username rolls a $randnum(1,21) for $msg          |Bot: AnkhHeart rolls a 18 for     |
|                          |                                                                                                         || !msg I wish I had 9 lives!                       |I wish I had 9 lives!             |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $botname                 |Displays the bot’s name                                                                                  |Hello I am $botname | !name                        |Bot: Hello I am StreamlabsBot!    |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $mychannel               |This will be replaced by the channel name where the bot is connected                                     |Connected to $mychannel | !mychannel               |Bot: Connected to AnkhHeart       |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $dummyormsg              |This will get replaced by anything behind the command. If there is nothing it be cleared from the        |http://api.com/$dummyormsg | !test Cats or !test   |Bot: http://api.com/Cats          |
|                          | response message.                                                                                       |                                                   | or http://api.com                |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $dummy                   |This is a Dummy that will not post the message if there is nothing behind the command                    |$dummy $readrandline(C:\Users\Ankh\Blah.txt) |     |Bot: Perhaps?!                    |
|                          |                                                                                                         |!8ball Am I green?                                 |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $arg1 to $arg9           |$arg1 will give you the first word after the command and $arg9 the ninth. If these parameters are in the |http://api.com/$dummyormsg | !test Cats or !test   |/me hugs says $arg1 $arg2! |      |
|                          |command it expects them to be there if they are not entered the command will not post.                   |                                                   | !argtest Hi Meow? Cookies?       |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $argl1 to $argl9         |$argl1 will give you the first word after the command and $argl9 the ninth but all in lower case. If     |/me hugs says $arg1 $arg2! |                       |Bot: hi meow?!                    |
|                          |these parameters are in the command it expects them to be there. the command will not run without them   | !argtest Hi Meow? Cookies?                        |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $num1 to $num9           |expects a valid integer                                                                                  |/me hugs says $arg1 $arg2! |                       |Bot hi meow?!                     |
|                          |                                                                                                         | !argtest Hi Meow? Cookies?                        |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $randnum(max) or         |Displays a random number in a specified range                                                            |/me rolls a $randnum(1,7)! | !roll                 |Bot rolls a 3!                    |
| $randnum(min,max)        |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $randquote               |Displays a random quote                                                                                  |$randextra | !randgif                              |Bot:                              |
|                          |                                                                                                         |                                                   |  http://randomURL.com/gif12.gif  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $quotes                  |Displays the amount of quotes                                                                            |There are $quotes quotes. | !quotes                |Bot: There are 123 quotes.        |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $randquote               |Displays a random quote                                                                                  |$randquote | !randquote                            |/Bot: I am not a cat! – AnkhHeart |
|                          |                                                                                                         |                                                   | [Thief] [01/01/2015]             |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+