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

        batch adds points to many users at once. blocks until the procedure is done

        Parameters
        -----------
        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`

        Returns
        ---------
        Dict[:class:`str`]
            a list of users that could not have points added to them

    .. function:: AddPointsAllAsync(data, callback)

        batch adds points to many users at once. returns immediately, and runs the callback when complete

         Parameters
        -----------
        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`
        :param callback: called when the operation is complete. should take a list of userids (:class:`str`) as its sole argument.
        :type callback: :class:`callable`

    .. function:: RemovePointsAll(data)

        batch removes points to many users at once. blocks until the procedure is done

        Parameters
        -----------
        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`

        Returns
        ---------
        Dict[:class:`str`]
            a list of users that could not have points removed from them

    .. function:: RemovePointsAllAsync(data, callback)

        batch removes points to many users at once. returns immediately, and runs the callback when complete

         Parameters
        -----------
        :param data: Dict[:class:`str` userid, :class:`int` amount]
        :type data: :class:`dict`
        :param callback: called when the operation is complete. should take a list of userids (:class:`str`) as its sole argument.
        :type callback: :class:`callable`

    .. function:: GetPoints(userid)

        retrieves a users points

        Parameters
        -----------
        :param userid: the userid of the user to get points for
        :type userid: :class:`str`

        Returns
        --------
        :class:`int` the points the user has

    .. function:: GetRank(userid)

        retrieves a users rank

        Parameters
        -----------
        :param userid: the userid of the user to get rank for
        :type userid: :class:`str`

        Returns
        --------
        :class:`str` the rank the user has

    .. function:: GetHours(userid)

        retrieves a users hours

        Parameters
        -----------
        :param userid: the userid of the user to get hours for
        :type userid: :class:`str`

        Returns
        --------
        :class:`float` the hours the user has watched for

    .. function:: GetTopCurrency(n)

        retrieves the top ``n`` users based on currency

        Parameters
        ------------
        :param n: the amount of users to get
        :type n: :class:`int`

        Returns
        --------
        Dict[userid: points] a dict of userids to points.

    .. function:: GetTopHours(n)

        retrieves the top ``n`` users based on hour

        Parameters
        ------------
        :param n: the amount of users to get
        :type n: :class:`int`

        Returns
        --------
        Dict[userid: points] a dict of userids to hours.

    .. function:: GetCurrencyUsers(userids)

        retrieves a list of :class:`~Currency` objects

        Parameters
        -----------
        :param userids: a list of userids
        :type userids: :class:`list`

        Returns
        --------
        a :class:`list` of :class:`~Currency` objects



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