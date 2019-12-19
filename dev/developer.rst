.. currentmodule:: Dev

.. _dev-docs:
.. _parent-object:

The Parent Object
=====================

.. class:: PythonManager

    Your main link to the chatbot

    .. function:: AddPoints(userid, username, amount)

        Adds points to the target user

        Parameters
        ----------------

        :param userid: the userid of the person you wish to add points to. On twitch this is generally the lowercase version of the username, but on mixer and youtube it will be something else
        :type userid: :class:`str`
        :param username: the username of the person you wish to add points to. this is not the same as the userid. it can be fetched using :meth:`~.GetDsiplayName`
        :type username: :class:`str`
        :param amount: the amount of points you wish to add
        :type amount: :class:`int`

        Returns
        --------

        :returns: :class:`bool` based on if the operation succeeded or not

    .. function:: RemovePoints(userid, username, amount)

        Removes points from the target user

        Parameters
        ----------------
-
        :param userid: :class:`str` the userid of the person you wish to remove points from. On twitch this is generally the lowercase version of the username, but on mixer and youtube it will be something else
        :param username: :class:`str` the username of the person you wish to remove points from. this is not the same as the userid. it can be fetched using :meth:`~.GetDsiplayName`
        :param amount: :class:`int` the amount of points you wish to remove

        Returns
        --------

        :returns: :class:`bool` based on if the operation succeeded or not

    .. function:: AddPointsAll(data)

        batch adds points to many users at once. blocks until the procedure is done

        Parameters
        ----------------

        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`

        Returns
        --------
-
        :returns: Dict[:class:`str`]
            a list of users that could not have points added to them

    .. function:: AddPointsAllAsync(data, callback)

        batch adds points to many users at once. returns immediately, and runs the callback when complete

         Parameters
        ----------------

        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`
        :param callback: called when the operation is complete. should take a list of userids (:class:`str`) as its sole argument.
        :type callback: :class:`callable`

    .. function:: RemovePointsAll(data)

        batch removes points to many users at once. blocks until the procedure is done

        Parameters
        ----------------

        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`

        Returns
        --------
-
        :returns: Dict[:class:`str`]
            a list of users that could not have points removed from them

    .. function:: RemovePointsAllAsync(data, callback)

        batch removes points to many users at once. returns immediately, and runs the callback when complete

         Parameters
        ----------------

        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`
        :param callback: called when the operation is complete. should take a list of userids (:class:`str`) as its sole argument.
        :type callback: :class:`callable`

    .. function:: GetPoints(userid)

        retrieves a users points

        Parameters
        ----------------

        :param userid: the userid of the user to get points for
        :type userid: :class:`str`

        Returns
        --------

        :returns: :class:`int` the points the user has

    .. function:: GetRank(userid)

        retrieves a users rank

        Parameters
        ----------------

        :param userid: the userid of the user to get rank for
        :type userid: :class:`str`

        Returns
        --------

        :returns: :class:`str` the rank the user has

    .. function:: GetHours(userid)

        retrieves a users hours

        Parameters
        ----------------

        :param userid: the userid of the user to get hours for
        :type userid: :class:`str`

        Returns
        --------

        :returns: :class:`float` the hours the user has watched for

    .. function:: GetTopCurrency(n)

        retrieves the top ``n`` users based on currency

        Parameters
        ----------------
-
        :param n: the amount of users to get
        :type n: :class:`int`

        Returns
        --------

        :returns: Dict[userid: points] a dict of userids to points.

    .. function:: GetTopHours(n)

        retrieves the top ``n`` users based on hour

        Parameters
        ----------------
-
        :param n: the amount of users to get
        :type n: :class:`int`

        Returns
        --------

        :returns: Dict[userid: points] a dict of userids to hours.

    .. function:: GetCurrencyUsers(userids)

        retrieves a list of :class:`~Currency` objects

        Parameters
        ----------------

        :param userids: a list of userids
        :type userids: :class:`list`

        Returns
        --------

        :returns: a :class:`list` of :class:`~Currency` objects

    .. function:: SendStreamMessage(text):

        sends a message to the stream chat

        Parameters
        ----------------

        :param text: the message to be sent
        :type text: :class:`str`

    .. function:: SendStreamWhisper(userid, text)

        sends a whisper to a viewer on stream

        .. important:: this only works on twitch. it does not work on youtube or mixer

        .. warning:: twitch whispers are *very* unreliable. Avoid using them if possible

        Parameters
        ----------------

        :param userid: the id of the user to send the message to
        :type userid: :class:`str`
        :param text: the message to whisper to the user
        :type text: :class:`str`


    .. function:: SendDiscordMessage(text):

        sends a message to the discord chat

        .. note:: this only works if the streamer has set up discord

        Parameters
        ----------------

        :param text: the message to be sent
        :type text: :class:`str`


    .. function:: SendDiscordDM(userid, text):

        sends a message to a specific discord user.

        .. note:: this only works if the streamer has set up discord

        Parameters
        ----------------

        :param userid: the id of the user to send the message to
        :type userid: :class:`str`
        :param text: the message to whisper to the user
        :type text: :class:`str`

    .. function:: BroadcastWSEvent(event_name, json_data)

        sends a message to connected overlays, should look something like

        .. code-block::
            Parent.BroadcastWSEvent("EVENT_SHOW_COUNTER", '{"show":false}')

        Parameters
        ----------------

        :param event_name: The name of the event.
        :type event_name: :class:`str`
        :param json_data: the json data associated with the event. usually you would pass the output of ``json.dumps``
        :type json_data: :class:`str`

    .. function:: HasPermission(userid, permission, info)

        checks if a user has a certain permission. a list of permissions can be found `here <link>`_.

        Parameters
        ----------------

        :param userid: a string with the userid of the target user
        :type userid: :class:`str`
        :param permission: a string containing the permission you wish to check for
        :type permission: :class:`str`
        :param info: only used for the min_rank, min_points, min_hours permissions. otherwise should be passed an empty string
        :type info: :class:`str`

        Returns
        --------

        :returns: :class:`bool`

    .. function:: GetViewerList()

        gets the current viewers

        Returns
        --------

        :returns: a :class:`list` of userids

    .. function:: GetActiveViewers()

        gets the current active chatters

        Returns
        --------

        :returns: a :class:`list` of userids

    .. function:: GetRandomActiveViewer()

        Returns
        --------

        :returns: :class:`str`

    .. function:: GetDisplayName(userid)

        gets a displayname based off the given userid

        Parameters
        ----------------
-
        :param userid: the userid to fetch a username for
        :type userid: :class:`str`

    .. function:: AddCooldown(script_name, command, seconds)

        Adds a cooldown to the internal cooldown manager

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`
        :param seconds: the amount of seconds the command should be on cooldown for
        :type seconds: :class:`int`

    .. function:: IsOnCooldown(script_name, command)

        checks if a command is on cooldown

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`

        Returns
        --------

        :returns: :class:`bool`

    .. function:: GetCooldownDuration(script_name, command)

        fetches the remainder of the cooldown

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`

        Returns
        --------

        :returns: :class:`int`

    .. function:: AddUserCooldown(script_name, command, user, seconds)

        Adds a user cooldown to the internal cooldown manager

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`
        :param user: the user to add a cooldown for
        :type user: :class:`str`
        :param seconds: the amount of seconds the command should be on cooldown for
        :type seconds: :class:`int`

    .. function:: IsOnUserCooldown(script_name, command, user)

        checks if a command is on user cooldown

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`
        :param user: the user to check for
        :type user: :class:`str`

        Returns
        --------

        :returns: :class:`bool`

    .. function:: GetUserCooldownDuration(script_name, command, user)

        fetches the remainder of the cooldown for a user

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param command: the name of the command on cooldown
        :type command: :class:`str`
        :param user: the user to fetch a cooldown for
        :type user: :class:`str`

        Returns
        --------

        :returns: :class:`int`

    .. function:: GetRequest(url, headers)

        GETs from an api

        Parameters
        ----------
        :param url: the url to get the request from
        :type url: :class:`str`
        :param headers: the headers for the api
        :type headers: :class:`dict`

    .. function:: PostRequest(url, headers, content, is_json=True)

        POSTs to an api

        Parameters
        ----------------

        :param url: the url to send the request to
        :type url: :class:`str`
        :param headers: the headers for the api
        :type headers: :class:`dict`
        :param content: the content to post
        :type content: Union[:class:`str`, :class:`dict`]
        :param is_json: indicates whether the data should be jsonified or not
        :type is_json: :class:`bool`

    .. function:: DeleteRequest(url, headers)

        DELETEs from an api

        Parameters
        ----------
        :param url: the url to send the request to
        :type url: :class:`str`
        :param headers: the headers for the api
        :type headers: :class:`dict`

    .. function:: PutRequest(url, headers, content, is_json=True)

        PUTs to an api

        Parameters
        ----------------

        :param url: the url to send the request to
        :type url: :class:`str`
        :param headers: the headers for the api
        :type headers: :class:`dict`
        :param content: the content to post
        :type content: Union[:class:`str`, :class:`dict`]
        :param is_json: indicates whether the data should be jsonified or not
        :type is_json: :class:`bool`

    .. function:: IsLive()

        indicates whether the stream is live or not

        Returns
        --------

        :returns: :class:`bool`

    .. function:: GetRandom(min, max)

        a replacement for the default `random` module, which is broken in ironpython. this can be fixed however, by doing the following

        .. code-block::
            import random
            random = random.WhichmannHill()

        Parameters
        ----------------

        :param min: the minimum number
        :type min: :class:`int`
        :param max: the maximum number
        :type max: :class:`int`

        Returns
        --------

        :returns: :class:`int`

    .. function:: GetStreamingService()

        gets the platform the streamer is streaming on

        Returns
        --------

        :returns: :class:`str`

    .. function:: GetChannelName()

        gets the channel name of the streamer.

        .. important:: this only works on twitch

        Returns
        --------

        :returns: :class:`str`

    .. function:: GetCurrencyName()

        gets the channels currency name

        Returns
        -------
        :returns: :class:`str`

    .. function:: Log(script_name, message)

        logs data to the chatbot's logging window

        Parameters
        ----------------

        :param script_name: the name of your script
        :type script_name: :class:`str`
        :param message: the message to log
        :type message: :class:`str`

    .. function:: PlaySound(file_path, volume)

        Attempts to play a sound, if possible, returns whether the sound was played or not

        Parameters
        ----------------

        :param file_path: the path of the file to play
        :type file_path: :class:`str`
        :param volume: a number between 0 and 1, how loud the sound should be
        :type volume: :class:`float`

        Returns
        --------
-
        :returns: :class:`bool`

    .. function:: GetQueue(n)

        Retrieves `n` number of people in the queue at the moment

        Parameters
        ----------------

        :param n: the amount of people to get
        :type n: :class:`int`

        Returns
        --------

        :returns: Dict[:class:`int`: :class:`str`]

    .. function:: GetSongQueue(max)

        gets the next `n` songs in the song queue

        Parameters
        ----------------

        :param n: the amount of songs to get
        :type n: :class:`int`

        Returns
        --------

        :returns: List[:class:`~Song`]

    .. function:: GetSongPlaylist(max)

        gets the next `n` songs in the playlist

        Parameters
        ----------------

        :param n: the amount of songs to get
        :type n: :class:`int`

        Returns
        --------

        :returns: List[:class:`~Song`]

    .. function:: GetNowPlaying()

        gets the current playing song

        Returns
        --------

        :returns: NamedTuple[Key: :class:`str`, Value: :class:`str`]


The Currency Object
=====================

.. _currency-object:

.. class:: Currency

    The class given when batch retrieving currency data

    .. attribute:: UserId

        :class:`str` the users id

    .. attribute:: UserName

        :class:`str` the users name

    .. attribute:: Points

        :class:`int` the users points

    .. attribute:: TimeWatched

        :class:`float` the users watch time

    .. attribute:: Rank

        :class:`str` the users rank

The Song Object
=================

.. _song-object::

.. class:: Song

    a song request, returned by GetSongQueue

    .. attribute:: Title

        :class:`str` the title of the song

    .. attribute:: RequestedBy

        :class:`str` the requester of the song. this is their userid

    .. attribute:: RequestedByName

        :class:`str` the requester of the song. this is their username

    .. attribute:: ID

        :class:`str` the id of the song

    .. attribute:: URL

        :class:`str` the URL of the song