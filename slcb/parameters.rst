.. _parameters:

Parameters
----------

.. _basic parameters:

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