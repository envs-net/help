[https://envs.net | environments](https://envs.net) - *since 9/2019*

> *write in irc/matrix channel `#envs`*<br />
> *for any help requests.*

# system info
more infos over the system and the installed packages can you find on the [sysinfo page](https://envs.net/sysinfo/).

# user account features
- terminal connection over [ssh and mosh](https://help.envs.net/help/#ssh)
- soft 1024mb/hard 1536mb limit on storage
- 200 process/threads at a time
- [e-mail](https://help.envs.net/mail/) (250mb mailbox storage)
- some more services like:<br />
  [website](https://help.envs.net/website/) /
  [blog](https://help.envs.net/blog/) /
  [databases](https://help.envs.net/database/) /
  [gopher](https://help.envs.net/gopher/) /
  [gemini](https://help.envs.net/gemini/) /
  [finger](https://help.envs.net/finger/) and much more.

# services

## # code related stuff
- [gitea](https://git.envs.net/) - git with a cup of tea. - lightweight code hosting solution<br />
members can be use your email credantials for login. (*user@envs.net* | *your email pw*)

## # general utilities
- [searx](https://searx.envs.net/) - privacy-respecting metasearch engine
- [cryptpad](https://pad.envs.net/) - collaborative real time editing
    - [cryptdrive](https://pad.envs.net/drive/)
    - [rich text](https://pad.envs.net/pad/)
    - [spreadsheets](https://pad.envs.net/sheet/)
    - [markdown/code editor](https://pad.envs.net/code/)
    - [presentation slides editor](https://pad.envs.net/slide/)
    - [polls](https://pad.envs.net/poll/)
    - [kanban boards](https://pad.envs.net/kanban/)
    - [whiteboard](https://pad.envs.net/whiteboard/)
    - [file drop](https://pad.envs.net/file/)
    - [todo lists](https://pad.envs.net/todo/)
    - [contacts](https://pad.envs.net/contacts/)
- [nullpointer](https://envs.sh) - file hosting and url shortener
- [privatebin](https://pb.envs.net/) - pastebin service
- [termbin](https://tb.envs.net/) - command line pastebin
- [tt-rss](https://rss.envs.net/) - news feed reader and aggregator
- [ip address info](https://ip.envs.net/)

## # social/communications
- [bbj](https://bbj.envs.net/) - forum
- [email](https://mail.envs.net/) - webmail
- [mailing lists](https://lists.envs.net/) - list archives are available [on the web here](https://lists.envs.net/hyperkitty/).
<br /><br />
- [getwtxt](https://twtxt.envs.net/) - microblogging for hackers - twtxt registry - see [twtxt](https://help.envs.net/blog/#with-twtxt) help page for more infos.
- [pleroma](https://pleroma.envs.net/) - microblogging - federated social network - [what is pleroma?](https://blog.soykaf.com/post/what-is-pleroma/)
    - **[envs news and blog](https://pleroma.envs.net/envs)**
    - [mastodon fe](https://pleroma.envs.net/web) - a webclient looks like mastodon
    - [halcyon](https://halcyon.envs.net/) - a twitter-like webclient
    - also available via gopher: `gopher://pleroma.envs.net` ([http proxy](https://gopher.envs.net/pleroma.envs.net/))
<br /><br />
- [matrix](https://matrix.envs.net/) - secure, decentralised, real-time communication. (with riot-web client and including audio- and video calls)
    - [dimension](https://dimension.envs.net/) - an open source integrations manager for matrix clients, like riot.
    - [jitsi-meet](https://jitsi.envs.net/) - secure, simple and scalable video conferences that you use as a standalone app or embed in your web application.
<br />
- ***note: we have a bridge between the channels `#envs` `#envs_news` `#envs_lounge` and `#envs_german` on matrix and irc.***
<br />
- [irc](https://envs.net/chat/irc) - irc network for the tildeverse
- [thelounge](https://webirc.envs.net/) - irc webclient - runs in private mode: it stays connected for you. run `webirc` to create a login.
- [znc](https://znc.envs.net/) - irc bouncer - please contact [creme](https://envs.net/~creme/) (via irc/matrix or email) to request an account, then log in with your email password and configure as needed.
<br /><br />
- [gopher proxy](https://gopher.envs.net/) - defaults to our local gopher: `gopher://envs.net`

## # dns-server
envs.net has her own dns master & slave server and use a additional slave from tildeverse.

| Name | Address | Location | Type |
| --- | --- | --- | --- |
| ns1.envs.net       | 89.163.145.170         | Düsseldorf | master |
| ns2.envs.net       | 78.31.64.115           | Düsseldorf | slave  |
| | | | |
| ns1.tildeverse.net | 198.50.128.75          | Montréal   | slave  |
| ns1.tildeverse.net | 2607:5300:203:5fd5::75 | Montréal   | slave  |

### master-zones:
- envs.net
- envs.sh
- envs.o
- envs.tilde

### slave server for:
- tildeverse.org / tildeverse.net
- tilde.team
    - ttm.sh
    - and some more aliases
