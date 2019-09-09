.. currentmodule:: Parameters

Parameters
===========

Basic Parameters
-----------------

+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+=========================================================================================================+===================================================+==================================+
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
| $randextra               |Displays a random value from the extra quotes                                                            |$randextra | !randgif                              |Bot:                              |
|                          |                                                                                                         |                                                   | http://randomURL.com/gif12.gif   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $maxquotes               |Displays the highest number quote                                                                        |There are $quotes quotes. Ranging from             |Bot: There are 123 quotes.        |
|                          |                                                                                                         |0 to $maxquotes.                                   | Ranging from 0 to 122.           |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $count                   |Counts amount of times a command has been used                                                           |/me has $count jars of salt. | !count              |Bot has 3 jars of salt. | Bot     |
|                          |                                                                                                         |                                                   |has 4  jars of salt. | Bot has    |
|                          |                                                                                                         |                                                   | 5 jars of salt | etc...          |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $checkcount(command)     |Displays the count of a specific command                                                                 |Cookie Count: $checkcount(!cookie) | !check        |Bot: Cookie Count: 10             |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $commands(               |Displays a list of all available commands for the user                                                   |Commands: $commands(3) | !commands or !commands    |Bot: Commands: !Cookie, !Slap,    |
| NumCommandsPerPage)      |                                                                                                         |(PageNumber)                                       | !Caster [Page 0/2]               |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $queuepos(targetid)      |This will display the target’s position in the queue                                                     |$username you are in Position $queuepos($userid)   |Bot: AnkhHeart you are in         |
|                          |                                                                                                         | | !MyPos                                          | Position 1                       |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $queue(amount)           |This will display the first X amount of people in the queue                                              |Next Up in Queue: $queue(3) | !NextUp              |Bot: Next Up in Queue: #0 anaki,  |
|                          |                                                                                                         |                                                   |#1 ankhheart, #2 xailran          |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$timers(NumTimersPerPage) |Displays a list of all available Timers                                                                  |Timers: $timers(3) | !timers or !timers            |Bot: Timers: !ctt, !twitter,      |
|                          |                                                                                                         | (PageNumber)                                      | !youtube [Page 0/1]              |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$date                     |Displays the Date based on the format under Quote Settings                                               |Currently it is $date                              |Bot: Currently it is 08/09/2015   |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$sfx(NumSFXPerPage)       |Displays a list of all available SFX for the user                                                        |SFX: $sfx(3) | !sfx or !sfx (PageNumber)           |Bot: SFX: !scream, !pika, !morph  |
|                          |                                                                                                         |                                                   | [Page 0/0]                       |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$time                     |Displays the caster’s time                                                                               |Currently it is $time over at AnkhHeart’s          |Bot: it is 10:20 PM over at       |
|                          |                                                                                                         | part of the world.                                | AnkhHeart’s part of the world.   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$currencyname             |Displays currencyname                                                                                    |In this channel you can collect $currencyname |    |Bot: In this channel you can      |
|                          |                                                                                                         | !currency                                         | collect Cookies!                 |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$nextsong and             |Return the current song that is being played through songrequest                                         |Current Song: $currentsong – Requested By          |Bot: Current song: ONE MORE FIGHT |
|$nextrequestedby          |                                                                                                         | $requestedby | !currentsong                       | – Requested By AnkhHeart         |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$nextsong and             |Return the current song that is next in queue                                                            |Next Song: $nextsong – Requested By                |Bot: Next song: ONE MORE FIGHT –  |
| $nextrequestedby         |                                                                                                         | $nextrequestedby | !nextsong                      |  Requested By AnkhHeart          |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$countdown(12:00 AM) or   |Allows you to start a countdown from the current time to the set time/date                               |$countdown(04/05/2015 12:00 AM) | !sleep           |Bot: 1 day 2 hours 48 minutes     |
|$countdown(04/05/2015     |                                                                                                         |                                                   | 36 seconds                       |
| 12:00 AM)                |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$countup(12:00 AM) or     |Allows you to set a start date for when the bot should start counting                                    |$countup(07/03/2016 12:00 AM) | !UsingStreamlabs   |Bot: 1 day 2 hours 48 minutes     |
|$countup(04/05/2015       |                                                                                                         | Chatbot                                           | 36 seconds                       |
| 12:00 AM)                |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$math[MathFunction]       |Allows you to perform math functions inside of Streamlabs Chatbot                                        |$math[10+5/2] | !Math                              |Bot: 12                           |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$extralifegoal            |Grabs your Extra Life goal                                                                               |$extralifegoal | !goal                             |Bot: 5000                         |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|$extralifeamount          |Grabs the amount you currently raised for Extra Life                                                     |$extralifeamount | !amount                         |Bot: 100                          |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+


Currency Parameters
+++++++++++++++++++

+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+=========================================================================================================+===================================================+==================================+
| $points                  |Displays the num of points of the user or target                                                         | $username has $points $currencyname | !cookies    | Bot: AnkhHeart has 1234 Cookies! |
|                          |                                                                                                         | or !cookies ankhheart                             |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $pointstext              |Displays the num of points of the user or target nicely formatted                                        | $username has $pointstext $currencyname |         | Bot: AnkhHeart has 1,234 Cookies |
|                          |                                                                                                         | !cookies or !cookies ankhheart                    |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $raids                   |Displays amount of times the user or target has raided the channel                                       | $username has raided the channel $raids time(s)   | Bot: AnkhHeart has raided the    |
|                          |                                                                                                         | so far! | !raids or !raids                        | channel 3 time(s) so far!        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $rank                    |Displays the users rank                                                                                  | $username is Rank: $rank | !rank or               | Bot: AnkhHeart is Rank:          |
|                          |                                                                                                         | !rank AnkhHeart                                   | Ninja Kitty                      |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $hours                   |Displays amount of hours the user has been in the stream for                                             | $username spent $hours in the stream! | !hrs      | Bot: AnkhHeart spent 10.5 hrs    |
|                          |                                                                                                         |                                                   | in the stream!                   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $level                   |Displays the users level                                                                                 | $username is Level $level! | !Lvl                 | Bot: AnkhHeart is Level 10       |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $toppoints(num)          |Displays top X amount of users based on points (Except Caster & Bots)                                    | Top 3: $toppoints(3) } !top3                      | Bot: Top 3: #1 Brain(1000), #2   |
|                          |                                                                                                         |                                                   |Kruiser8(999),#3 EdeMonster(998)  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $tophours(num)           |Displays top X amount of users based on hours(Except Caster & Bots)                                      | Top 2: $tophours(2) | !top2                       | Bot: Top 2: #1 Decius(123,       |
|                          |                                                                                                         |                                                   | Hrs) #2 Ocgineer(120 Hrs)        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $pointspos               |Displays the users position in the ranking based on amount of points                                     | $username is ranked #$pointspos | !mypos          | Bot: AnkhHeart is ranked #1      |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $hourspos                |Displays the users position in the ranking based on amount of hours                                      | $username is ranked #$hourspos | !hrspos          | Bot: AnkhHeart is ranked #2      |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $nxtrankreq              |Displays the amount of points/hours the user requires for his next rank                                  | $username, You need $nxtrankreq points to become  | Bot: AnkhHeart, You need 13      |
|                          |                                                                                                         | a $nxtrank!                                       | points to become a Ninja Kitty!  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $addpoints("targetid",   |Adds points to a certain user and sends a message upon succeeding / failing                              | $addpoints("ankhheart","10","50","ankhheart Got   | Bot: AnkhHeart got 25 points     |
|"min","max","succeed",    |                                                                                                         | $value points","Failed to give points!") |        |                                  |
|"fail")                   |                                                                                                         | !addpoints                                        |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $removepoints("targetid" |Removes points from a certain user and sends a message upon succeeding/failing. Force remove(true/false) | $removepoints("ankhheart","10","100","Removed     | Bot: Removed 85 points from      |
|,"min","max","succeed",   | removes points even if the user doesn’t have enough.                                                    |$value points from ankhheart.","Unable To remove   |  ankhheart.                      |
|"fail","forceremove true  |                                                                                                         |$value points from ankhheart!","false") |          |                                  |
| or false")               |                                                                                                         |!removepoints                                      |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $removepoints("targetid" |Removes points from a certain user and sends a message upon succeeding/failing. Force remove(true/false) | $removepoints("ankhheart","10","100","Removed     | Bot: Removed 85 points from      |
|,"min","max","succeed",   | removes points even if the user doesn’t have enough.                                                    |$value points from ankhheart.","Unable To remove   |  ankhheart.                      |
|"fail","forceremove true  |                                                                                                         |$value points from ankhheart!","false") |          |                                  |
| or false")               |                                                                                                         |!removepoints                                      |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $givepoints("fromid",    |Gives points from one person to another.                                                                 |$givepoints("$userid","$targetid","50","$username  | Bot: AnkhHeart gave 50 points    |
|"toid","num","succeed",   |                                                                                                         |gave $value points to $targetname","$username      | to Must13                        |
|"fail","forcegive true or |                                                                                                         |didn't have enough points to give to $targetname!" |                                  |
|false")                   |                                                                                                         |,"false") | !give gamegooru21                      |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $value                   |[Only Works inside of $addpoints, $givepoints or $removepoints]                                          | [see above example]                               | [see above example]              |
|                          |Gets replaced with the random value between min & max                                                    |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $newbalance(targetid)    |[Only Works inside of $addpoints, $givepoints or $removepoints]                                          | $givepoints("$userid","$targetid","50","$username |Bot: AnkhHeart gave 50            |
|                          |Gets replaced with the remaining balance after a $removepoints, $addpoints or $givepoints transaction    |gave $value points to $targetname.$targetname:     |gamegooru21. AnkhHeart 50         |
|                          |                                                                                                         |$newbalance($targetid) points remaining.","fail"   |remaining                         |
|                          |                                                                                                         |,"false") | !give gamegooru21                      |                                  |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+

Twitch API Parameters
+++++++++++++++++++++

+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+=========================================================================================================+===================================================+==================================+
| $userurl                 |Displays the user’s twitch channel URL                                                                   | $user’s twitch channel is: $userurl | !userurl    | Bot: AnkhHeart’s twitch channel  |
|                          |                                                                                                         |                                                   | is: http://twitch.tv/AnkhHeart   |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $usergame                |Displays the user’s last played/current game                                                             |$user’s was/is playing: $usergame | !usergame      | Bot: AnkhHeart was/is playing:   |
|                          |                                                                                                         |                                                   | Bloodborne                       |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $userstatus              |Displays the user’s stream title                                                                         | $user’s Stream title is: $userstatus |            | Bot: AnkhHeart’s Stream title    |
|                          |                                                                                                         | !userstatus                                       |is: [720p] Fable: The Lost        |
|                          |                                                                                                         |                                                   |Chapters [PC]                     |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $url                     |Displays the target’s twitch channel URL                                                                 |$targetname can be found streaming at: $url |      | Bot: AnkhHeart can be found      |
|                          |                                                                                                         |!url AnkhHeart                                     |streaming at:                     |
|                          |                                                                                                         |                                                   |http://twitch.tv/AnkhHeart        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $game                    |Displays the target’s current/last played game                                                           |$targetname has last played: $game | !game         |Bot: AnkhHeart has last played:   |
|                          |                                                                                                         |AnkhHeart                                          |Bloodborne                        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $status                  |Displays the target’s stream title                                                                       |$targetname Stream title is: $title | !title       |Bot: AnkhHeart Stream title is:   |
|                          |                                                                                                         |AnkhHeart                                          |[720p] Fable: The Lost Chapters   |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $myurl                   |Displays the twitch channel URL for your stream                                                          |My channel is: $myurl. | !myurl                    |Bot: My channel is:               |
|                          |                                                                                                         |                                                   |http://twitch.tv/AnkhHeart        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $mygame                  |Displays the game you are currently playing                                                              |I am playing: $mygame | !currentgame               |Bot: I am playing: Bloodborne     |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $mystatus                |Displays your stream title                                                                               |Status: $mystatus | !mystatus                      |Bot: Status: [720p] Fable: The    |
|                          |                                                                                                         |                                                   |Lost Chapters [PC]                |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $uptime                  |Displays for how long the stream has been Live                                                           |The stream has been live for: $uptime | !uptime    |Bot: The stream has been live     |
|                          |                                                                                                         |                                                   |for: 1 hour 25 minutes 58 seconds |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $followercount           |Displays your streams follower count                                                                     |AnkhHeart has $followercount followers!            |Bot: AnkhHeart has 1070           |
|                          |                                                                                                         | | !followercount                                  | followers!                       |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $subcount                |Displays your streams sub count                                                                          |AnkhHeart has $subcount subs! !subcount            |Bot: AnkhHeart has 0 subs!        |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $currenthosts            |Displays everyone that is currently hosting the stream (Only works when you’re live)                     |Current Hosts: $currenthosts(2)                    |Bot: Current Hosts: EdeMonster,   |
|(NumHostsPerPage)         |                                                                                                         |                                                   |Promouse [Page 0/1]               |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $setgame(game) and       |Allows you to set the game & title through a command and create presets for certain games                |$setgame(Dungeon Defenders II)                     |No response as the bot will       |
| $settitle(title)         |                                                                                                         |$settitle(MMO Mornings)  | !dd2                    |simply update the game & title    |

File Reading Parameters
------------------------

+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+=========================================================================================================+===================================================+==================================+
| $readline(FileLocation)  |Reads the first line of the document                                                                     |$readline(C:\test.txt) | !currentsong              |Bot: Currently playing: Popskyy   |
|                          |                                                                                                         |                                                   |- Rize Up                         |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $readrandline            |Reads a random line from the file                                                                        |/me slaps $randusername with a                     |Bot slaps AnkhHeart with a Tuna | |
|(FileLocation)            |                                                                                                         |$readrandline(C:\test2.txt) | !slap                |slaps AnkhHeart with a Brick(etc) |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $readspecificline        |Reads a specific line from the file (Starts from 0)                                                      |/me slaps $randusername with a                     |Bot slaps AnkhHeart with a        |
| (FileLocation,LineNum)   |                                                                                                         |$readspecificline(C:\test2.txt,3)! | !slap         | Shovel!                          |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $mygame                  |Displays the game you are currently playing                                                              |I am playing: $mygame | !currentgame               |Bot: I am playing: Bloodborne     |
|                          |                                                                                                         |                                                   |                                  |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+

Custom API Parameter
---------------------


+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter               | Description                                                                                             | Example Command                                   | Example Output                   |
+==========================+=========================================================================================================+===================================================+==================================+
| $readapi(URL)            |Displays the text on the URL’s page. Max 500 characters                                                  |$readapi(                                          |Bot: 1. BensGaming808, 2.         |
|                          |                                                                                                         |https://nightdev.com/hosted/followers.php?channel  |Gamakuro, 3. GENERAL_XROS,        |
|                          |                                                                                                         |=ankhheart&limit=5)                                |4. wulleybully, 5. NorQuel        |
+--------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+

File Saving Parameters
-----------------------

+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter                  | Description                                                                                             | Example Command                                   | Example Output                   |
+=============================+=========================================================================================================+===================================================+==================================+
|$overwritefile("fileLocation | Overwrites all the data in the .txt file with the added text                                            |$overwritefile("C:\test.txt","$msg","Succeeded     |Bot: Succeeded!                   |
|","Text") And                |                                                                                                         |:D","Failed! ") | !save I am a cat                 |                                  |
|$overwritefile("fileLocation |                                                                                                         |                                                   |                                  |
|","Text","Succeed","Fail")   |                                                                                                         |                                                   |                                  |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+


Miscellaneous Parameters
-------------------------

+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
|  Parameter                  | Description                                                                                             | Example Command                                   | Example Output                   |
+=============================+=========================================================================================================+===================================================+==================================+
| $months                     |Only usable in the Twitch Resub Notification                                                             |$username just subbed for $months months in a row! |Bot: AnkhHeart just subbed for    |
|                             |                                                                                                         |                                                   |3 months in a row!                |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $bits / $totalbits          |Only usable in the Cheer Chat Notification                                                               |$username just cheered $bits bits for a total of   |Bot: AnkhHeart just cheered 100   |
|                             |                                                                                                         |$totalbits bits!                                   |bits for a total of 1234 bits!    |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $donationmsg                |Only usable in the Streamlabs Chat Notification                                                          |$username just donated $amount USD! Message:       |Bot: AnkhHeart just donated 10    |
|                             |                                                                                                         |$donationmsg                                       |USD! Message: Harro <3            |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $donationmsg                |Only usable in the Streamlabs Chat Notification                                                          |$username just donated $amount USD! Message:       |Bot: AnkhHeart just donated 10    |
|                             |                                                                                                         |$donationmsg                                       |USD! Message: Harro <3            |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
| $viewers                    |Only usable in the Host Chat Notification                                                                |$username just hosted you for $viewers viewer(s)!  |Bot: AnkhHeart just hosted you    |
|                             |                                                                                                         |                                                   |for 10 viewer(s)!                 |
+-----------------------------+---------------------------------------------------------------------------------------------------------+---------------------------------------------------+----------------------------------+
