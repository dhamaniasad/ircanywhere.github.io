CommandManager
==============

*(c) 2013-2014 http://ircanywhere.com*

**Author:** Ricki Hastings

IRCAnywhere server/commands.js
 
.. js:class:: CommandManager.CommandManager()

   Responsible for handling all incoming commands from websocket clients

   :returns: void

.. js:function:: CommandManager.init()

   Called when the application is booted and everything is ready, sets up an observer
   on the commands collection for inserts and handles them accordingly.
   Also sets up aliases, this should not be recalled, although can be extended to setup
   your own aliases.

   :returns: void

.. js:function:: CommandManager._ban(client, channel, nickname, ban)

   Sets +b/-b on a specific channel on a chosen client, not extendable
   and private.

   :param object client: A valid client object
   :param string channel: A channel name
   :param string nickname: A nickname or hostname to ban
   :param boolean ban: Whether to ban or unban
   :returns: void

.. js:function:: CommandManager.createAlias(command, alias)

   Creates an alias from the first parameter to the remaining ones.
   
   Examples: ::
    
       commandManager.createAlias('/part', '/p', '/leave');
       // sets an alias for /p and /leave to forward to /part

   :param string command: A command to alias
   :param ...string alias: A command to map to
   :returns: void

.. js:function:: CommandManager.parseCommand(user, client, target, command)

   Parse a command string and determine where to send it after that based on what it is
   ie just text or a string like: '/join #channel'

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string command: The command string
   :returns: void

.. js:function:: CommandManager.msg(user, client, target, params, out, id)

   '/nickserv' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :param boolean out: Used to force the message to target or params[0]
   :param objectid id: The object id of the command so we can remove it if we need to
   :returns: void

.. js:function:: CommandManager.msg(user, client, target, params, out, id)

   '/msg' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :param boolean out: Used to force the message to target or params[0]
   :param objectid id: The object id of the command so we can remove it if we need to
   :returns: void

.. js:function:: CommandManager.notice(user, client, target, params)

   '/notice' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.me(user, client, target, params)

   '/me' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.join(user, client, target, params)

   '/join' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.part(user, client, target, params)

   '/part' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.cycle(user, client, target, params)

   '/cycle' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.topic(user, client, target, params)

   '/topic' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.mode(user, client, target, params)

   '/mode' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.invite(user, client, target, params)

   '/invite' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.kick(user, client, target, params)

   '/kick' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.kickban(user, client, target, params)

   '/kickban' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.ban(user, client, target, params)

   '/ban' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.unban(user, client, target, params)

   '/unban' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.nick(user, client, target, params)

   '/nick' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.ctcp(user, client, target, params)

   '/ctcp' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.away(user, client, target, params)

   '/away' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.unaway(user, client)

   '/unaway' command

   :param object user: A valid user object
   :param object client: A valid client object
   :returns: void

.. js:function:: CommandManager.close(user, client, target)

   '/close' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :returns: void

.. js:function:: CommandManager.query(user, client, target)

   '/query' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :returns: void

.. js:function:: CommandManager.quit(user, client)

   '/quit' command

   :param object user: A valid user object
   :param object client: A valid client object
   :returns: void

.. js:function:: CommandManager.reconnect(user, client)

   '/reconnect' command

   :param object user: A valid user object
   :param object client: A valid client object
   :returns: void

.. js:function:: CommandManager.list(user, client, target, params)

   '/list' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.whois(user, client, target, params)

   '/whois' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void

.. js:function:: CommandManager.raw(user, client, target, params)

   '/raw' command

   :param object user: A valid user object
   :param object client: A valid client object
   :param string target: Target to send command to, usually a channel or username
   :param string params: The command string
   :returns: void