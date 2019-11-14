[https://envs.net | environments](https://envs.net)

> *write in irc (#envs) or*<br />
> *contact [sudoers@envs.net](mailto:sudoers@envs.net) for any help requests.*

# System Info
more infos over the system and the installed packages can you find on the [sysinfo page](https://envs.net/sysinfo/).

# Services

## # code related stuff
- [gitea](https://git.envs.net/) - members can be use your email credantials for login. (*user@envs.net* | *your email pw*)

## # general utilities
- [searx](https://searx.envs.net/) - privacy-respecting metasearch engine
- [cryptpad](https://pad.envs.net/) - collaborative real time editing
    - [cryptdrive](https://pad.envs.net/drive/)
    - [rich text](https://pad.envs.net/pad/)
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
- [rss reader](https://rss.envs.net/) - news feed reader and aggregator
- [ip address info](https://ip.envs.net/)

## # social/communications
- [bbj](https://bbj.envs.net/) - forum
- [email](https://mail.envs.net/) - webmail, smtp/imap, mutt, neomutt
- [mailing lists](https://lists.envs.net/) - list archives are available [on the web here](https://lists.envs.net/hyperkitty/).
<br /><br />
- [irc](https://envs.net/chat/) - irc network for the tildeverse
- [thelounge](https://webirc.envs.net/) - irc webclient - runs in private mode: it stays connected for you. run `webirc` to create a login.
- [znc](https://znc.envs.net/) - irc bouncer - log in with username and your email password
<br /><br />
- [gopher proxy](https://gopher.envs.net/) - defaults to our local gopher: `gopher://envs.net`
- [getwtxt](https://twtxt.envs.net/) - twtxt registry - microblogging - more on [twtxt](https://help.envs.net/blog/#with-twtxt) help page

## # DNS-Server
envs.net has her own dns-master server and use the secondary servers from tildeverse.

[repo on gitea](https://git.envs.net/envs/DNS/)

| Name | Address | Location | Type |
| --- | --- | --- | --- |
| ns1.envs.net       | 89.163.145.170        | Düsseldorf | master |
| ns2.envs.net       | 78.31.64.115          | Düsseldorf | slave  |
| | | | |
| ns1.tildeverse.net | 51.79.32.63           | Montréal   | slave  |
| ns1.tildeverse.net | 2607:5300:60:823f::63 | Montréal   | slave  |

### master-zones:
- envs.net
- envs.sh
- envs.o
- envs.tilde

### slave server for:
- tildeverse.org
- tilde.team
