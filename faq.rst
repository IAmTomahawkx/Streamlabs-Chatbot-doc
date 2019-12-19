.. _faq:

FAQ
====

Where'd My Scripts Tab Go????
------------------------------
This is probably the most frequently asked question we get.
The :ref:`scripts <scripts>` tab only shows up if you have valid Streamer/ Bot account tokens. If your :ref:`scripts <scripts>` isn't showing up,
it most likely means your token(s) are invalid. Go to Settings (gear icon, bottom left) > Streamer/Bot > Generate Token >
Connect. That should solve the case of the disappearing tab

Songrequest links
---------------------
The default setting for :ref:`Song Requests <song-requests>` allows for only direct youtube links. you can change this by going into the
:ref:`Song Requests <song-requests>` settings, changing the *mode* from **$id** to either of the **$readapi** options. Now you should be able to
request songs by name.

Bot not responding
---------------------
Your tokens are probably expired. You need to You need to :ref:`regenerate them <regenerating-tokens>`


Local and extension currency. What's the difference?
------------------------------------------------------
The local currency is stored directly in the bot, and allows for more customization.
The extension currency is stored in the cloud, and syncs to the streamlabs currency. this does not allow as much customization.

Notifications aren't working
-------------------------------
Click the 👤 in the bottom left corner of the bot and go to streamlabs

- Disconnect from streamlabs
- Generate token (make sure it's using the streamer account)
- Connect to streamlabs

.. note:: you also need to have any widget open. Alert box/event list/ chat box/streamlabels/ Streamlabs OBS

Can't update game/tile through dashboard or command
-----------------------------------------------------
You need to :ref:`regenerate your tokens <regenerating-tokens>`

Notifications aren't working
------------------------------
You need to :ref:`regenerate your tokens <regenerating-tokens>`

.. _regenerating-tokens:

How do I regenerate my tokens?
--------------------------------
You can regenerate your tokens by going to 👤 (bottom left corner), clicking on ``Streamer Account``, pressing ``disconnect``, then ``generate token``, then ``connect``.
repeat this process for the ``Bot Account``, and ``Streamlabs``

.. _faq-discord:

Discord
---------

How do I connect the bot to my Discord server?
+++++++++++++++++++++++++++++++++++++++++++++++++
We made two guides for that, one for the `Bot Owner <https://howto.streamlabs.com/streamlabs-chatbot-22/connecting-chatbot-to-discord-desktop-2173>`_
and one for `Everyone Else <https://howto.streamlabs.com/streamlabs-chatbot-22/link-discord-and-twitch-in-chatbot-desktop-2269>`_

Can the bot connect to more than one channel in my Discord?
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
No not right now

Commands in Discord only works for me and nobody else?
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Everyone that wants to use the bot in Discord must follow the steps in `this <https://howto.streamlabs.com/streamlabs-chatbot-22/link-discord-and-twitch-in-chatbot-desktop-2269>`_
guide.

.. _faq-scripts:

Scripts
--------

How do i get started with scripts?
+++++++++++++++++++++++++++++++++++++
It only takes a few minutes and have a guide for it
`here <https://howto.streamlabs.com/streamlabs-chatbot-13/using-scripts-in-streamlabs-chatbot-460>`_

How do I add an overlay from a script?
+++++++++++++++++++++++++++++++++++++++
Follow the steps in `this guide <https://github.com/StreamlabsSupport/Streamlabs-Chatbot/wiki/Script-overlays>`_

Where do I find documentation for scripts?
+++++++++++++++++++++++++++++++++++++++++++++
there will be new documentation coming as part of this documentation, but for now you can see the original documentation over at
https://github.com/AnkhHeart/Streamlabs-Chatbot-Python-Boilerplate/wiki