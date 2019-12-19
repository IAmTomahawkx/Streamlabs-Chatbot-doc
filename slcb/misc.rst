.. currentmodule:: Streamlabs Chatbot (Twitch)

Generated Text Files
=====================
The bot automatically generates text files that can be used to display information on stream.
These files can be found in the Bot's Install Directory -> Services -> Twitch -> Files folder.
If you don't remember where you installed the bot just Right click on its shortcut and select Open File Location.
If this leads you to the Startup folder instead do it once more on the shortcut there and eventually you will end up in the Bot's install Directory.

+--------------------------------------+--------------------------------------+
|Filename                              |Description                           |
+======================================+======================================+
|AmountOfFollowers.txt                 |Follower Amount (per session)         |
+--------------------------------------+--------------------------------------+
|Followers.txt                         |New Follower List (per session)       |
+--------------------------------------+--------------------------------------+
|RecentFollower.txt                    |Last Follower                         |
+--------------------------------------+--------------------------------------+
|AmountOfHosts.txt                     |Host Amount (per session)             |
+--------------------------------------+--------------------------------------+
|Hosts.txt                             |New Hosts (per session)               |
+--------------------------------------+--------------------------------------+
|RecentHost.txt                        |Last Host                             |
+--------------------------------------+--------------------------------------+
|AmountOfSubs.txt                      |Twitch Sub Amount (per session)       |
+--------------------------------------+--------------------------------------+
|Subs.txt                              |New Subs (per session)                |
+--------------------------------------+--------------------------------------+
|RecentSub.txt                         |Last Sub                              |
+--------------------------------------+--------------------------------------+
|CurrentSong.txt                       |Current Song                          |
+--------------------------------------+--------------------------------------+
|RequestedBy.txt                       |Requested By                          |
+--------------------------------------+--------------------------------------+
|CurrentlyPlaying.txt                  |Complete Current Song + Requested By  |
+--------------------------------------+--------------------------------------+
|Deaths.txt                            |Death Counter                         |
+--------------------------------------+--------------------------------------+
|Streamlabs_Recent_Donator.txt         |Recent Donator                        |
+--------------------------------------+--------------------------------------+
|ExtraLife.txt                         |Extra Life (Raised / Goal)            |
+--------------------------------------+--------------------------------------+
|ExtraLife_Team.txt                    |Extra Life Team (Raised / Goal)       |
+--------------------------------------+--------------------------------------+
|ExtraLife_Donators.txt                |Extra Life Donations (per Session)    |
+--------------------------------------+--------------------------------------+
|ExtraLife_Recent_Donator.txt          |Extra Life Last Donator               |
+--------------------------------------+--------------------------------------+

.. _scripts:

Scripting
==========
Scripting is a great way to take the Streamlabs Chatbot further in what it can do.

Setup
-----
To use scripts, you'll need two thing.

- you'll need to install Python 2.7. You can download it `Here <https://www.python.org/ftp/python/2.7.13/python-2.7.13.msi>`_.
  After installing Python, you will need to open the settings in the scripts tab of your chatbot, select Folder, and set it
  to **C:\\Python27\\Lib** . This can vary from the one that I am referring to since it all depends on where you installed Python.
  Once you've found the Lib folder select it and hit Save.

.. warning::
  Do **not** use *any* other version of Python. It will not work for the chatbot.

- you'll need scripts *(surprise!)*. although any scripts you find online will (most likely) *work*, they could cause harm
  to your computer. Scripts do have access to all your files (as any program does) and you need to be cautious when installing
  them. On the Streamlabs Chatbot discord (note that it is separate from the Streamlabs discord), you will find scripts that
  have been checked by trusted staff, and are safe to use.

Importing Scripts
------------------
Importing a script is simple. Simply click the Import Button in the Scripts Tab, Navigate to the Zip File and Open it.
Afterwards the bot will import the script for you and reload your scripts so it's ready to go.

Assigning API key to scripts
-----------------------------
Whenever you right click on a script you’re able to select \`Insert Api Key\` which will put a small .js file in the
script’s folder that will give it access to connect to the chatbot’s websocket server.
The Api Key in question can be refreshed whenever you wish. Though in this case you will need to update each client.js
file so it uses the appropriate key. This key is used as a password so only clients which you have granted access may
connect to the server.

If a script asks for the api key inside it's UI, here's one way you can get it:
.. image:: /images/instructions.jpg
    :alt: How to get your API key off the Website

Creating Scripts
-----------------
*One of Us! One of Us!*
If you're going to create scripts, check out the `boilerplate <https://github.com/AnkhHeart/Streamlabs-Chatbot-Python-Boilerplate>`_
and the `wiki <https://github.com/AnkhHeart/Streamlabs-Chatbot-Python-Boilerplate/wiki>`_

Also, join us in **Script-Devs** on the Streamlabs Chatbot `discord server <https://discord.gg/xFcsxft>`_!