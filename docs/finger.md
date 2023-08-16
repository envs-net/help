the finger protocol was created way back in 1977. its purpose was to display information about the queried user of a system, or all the users of a system.

# # user finger

here on envs.net, we run efingerd. see `man efingerd` for more info.<br />
you can create a script called `~/.efingerd` which will be run when anyone fingers you.

## querying
the standard query for finger is simply

`finger username@envs.net`

which displays login name, home directory, shell, real name, current login time, idle time, whether or not the user has mail, and the contents of the user's `~/.plan`, `~/.project` and `~/.tz` file.

## .plan
the `~/.plan` file displayed at the end of the finger query response allows for some customization. you can put literally any text you want there. status updates, summaries, etc. this little file allows us to use finger as a rudimentary social network.

for example, say you want to use it as a personal summary, like having a blurb about what you're working on. place the statement into `~/.plan` and you're ready to go!

for a more traditional social network style format, put dated and timed status updates as if you're tooting on a mastodon instance. the sky's the limit! Well, actually, text is the limit. but you get the idea. right?

## .pronouns
save your pronouns in your `~/.pronouns` file.

## .project
in the `~/.project` file you can deposit information about your projects.

## .tz
the `~/.tz` file displays your timezone informations.

example:<br />
&nbsp;&nbsp;`Europe/Berlin`

hope to see you on finger soon!
