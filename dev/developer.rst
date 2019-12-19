.. currentmodule:: Dev

.. _dev-docs:

.. class:: PythonManager
    Your main link to the chatbot

    .. function:: AddPoints(userid, username, amount)
        Adds points to the target user

        Parameters
        -----------
        :param userid: the userid of the person you wish to add points to. On twitch this is generally the lowercase version of the username, but on mixer and youtube it will be something else
        :type userid: :class:`str`
        :param username: the username of the person you wish to add points to. this is not the same as the userid. it can be fetched using :meth:`~.GetDsiplayName`
        :type username: :class:`str`
        :param amount: the amount of points you wish to add
        :type amount: :class:`int`


    .. function:: RemovePoints(userid, username, amount)
        Removes points from the target user

        Parameters
        ------------
        :param userid: :class:`str` the userid of the person you wish to remove points from. On twitch this is generally the lowercase version of the username, but on mixer and youtube it will be something else
        :param username: :class:`str` the username of the person you wish to remove points from. this is not the same as the userid. it can be fetched using :meth:`~.GetDsiplayName`
        :param amount: :class:`int` the amount of points you wish to remove

    .. function:: AddPointsAll(data)
        batch adds points to many users at once

        Parameters
        -----------
        data: Dict[:class:`str` userid, :class:`int` amount]
