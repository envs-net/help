# envs.net ~ help page

[https://envs.net | environments](https://envs.net) - *since 9/2019*

> *write on irc `#envs` at irc.tilde.chat*<br />
> *for any help requests and community support.*

**[> envs news and blog on pleroma](https://pleroma.envs.net/envs)**

***

## shell user account features
- terminal connection over [ssh and mosh](https://help.envs.net/help/#ssh)
- 200 process/threads at a time
- soft 1024mb / hard 1536mb limit on storage
- [e-mail](https://help.envs.net/mail/) (250mb mailbox storage)

  *if you need more (mailbox-)storage space for your work then feel free to contact us.*

- some more services like:  
  [website](https://help.envs.net/website/) /
  [webring](https://envs.net/ring/) /
  [blog](https://help.envs.net/blog/) /
  [databases](https://help.envs.net/database/) /
  [gopher](https://help.envs.net/gopher/) /
  [gemini](https://help.envs.net/gemini/) /
  [finger](https://help.envs.net/finger/) /
  and much more ..

## services

!!! note
    the checkboxes after the service name show you whether it can be used with the shell account or not.  

    `[x]` - you can use with your shell account  
    `[-]` - no account is required or can be created  
    `[ ]` - an account must be created

### # code related stuff
- [gitea](https://git.envs.net/) `[x]` - git with a cup of tea. - lightweight code hosting solution.  
members can be use your email credantials for login. (*username@envs.net* | *your email pw*)
    - [drone](https://drone.envs.net/) - drone is a container-native, continuous delivery platform.  
    (includes a "drone-ssh-runner" and "drone-docker-runner".)

### # general utilities
- [searxng](https://searx.envs.net/) `[-]` - privacy-respecting metasearch engine
- [privatebin](https://pb.envs.net/) `[-]` - pastebin service
- [hedgedoc](https://hedgedoc.envs.net/) `[-]` - collaborative real time markdown
- [cryptpad](https://pad.envs.net/) `[-]` - collaborative real time editing
    - [cryptdrive](https://pad.envs.net/drive/)
    - [rich text](https://pad.envs.net/pad/)
    - [spreadsheets](https://pad.envs.net/sheet/)
    - [markdown/code editor](https://pad.envs.net/code/)
    - [presentation slides editor](https://pad.envs.net/slide/)
    - [polls](https://pad.envs.net/form/)
    - [kanban boards](https://pad.envs.net/kanban/)
    - [whiteboard](https://pad.envs.net/whiteboard/)
    - [file drop](https://pad.envs.net/file/)
    - [contacts](https://pad.envs.net/contacts/)
- [ip address info](https://ip.envs.net/) `[-]`
- [ntfy](https://ntfy.envs.net/) `[-]` - simple http-based notification service

### # social / communications
- [bbj](https://bbj.envs.net/) `[x]` - forum
- [email](https://mail.envs.net/) `[x]` - webmail
- [mailing lists](https://lists.envs.net/) `[-]` - list archives are available [on the web here](https://lists.envs.net/hyperkitty/).
<br /><br />
- [gopher proxy](https://gopher.envs.net/) `[x]` - defaults to our local gopher: `gopher://envs.net`<br />(on port 70)
- [gemini proxy](https://gemini.envs.net/) `[x]` - defaults to our local gemini: `gemini://envs.net`<br />(on port 1965)
<br /><br />
- [getwtxt](https://twtxt.envs.net/) `[ ]` - microblogging for hackers - twtxt registry - see [twtxt](https://help.envs.net/blog/#with-twtxt) help page for more infos.
- [pleroma](https://pleroma.envs.net/) `[ ]` - microblogging - federated social network - _[what is pleroma?](https://blog.soykaf.com/post/what-is-pleroma/)_
<br /><br />
- [xmpp](https://envs.net/chat/xmpp/) `[x]` - our self-hosted jabber/xmpp instance for local envs users.
    - [webchat](https://webchat.envs.net/) `[-]` - jabber/xmpp converse.js webclient
<br /><br />
- [irc](https://envs.net/chat/irc/) `[-]` - irc network for the tildeverse
    - [thelounge](https://webirc.envs.net/) `[x]` - irc webclient - runs in private mode: it stays connected for you. run `webirc` to create a login.
    - [znc](https://znc.envs.net/) `[ ]` - irc bouncer - please contact [creme](https://envs.net/~creme/) (via email) to request an account, then log in with your `username` and email password and configure as needed.

### # public dns-server
***note:*** *query/request logging is off!*

**host:** `dns.envs.net`  
**ipv4:** `157.180.15.214`  
**ipv6:** `2a01:4f9:3100:3b2b:0:a:0:21`  
**port:** `53`

#### dns-over-https (doh)

**server address / url:** `https://dns.envs.net/dns-query`

#### dns-over-tls (dot)

**host:** `dns.envs.net`  
**ipv4:** `157.180.15.214`  
**ipv6:** `2a01:4f9:3100:3b2b:0:a:0:21`  
**port:** `853`  


**example unbound config  (`/etc/unbound/unbound.conf`)**
```
include-toplevel: "/etc/unbound/unbound.conf.d/*.conf"

server:
  verbosity: 2
  tls-cert-bundle: /etc/ssl/certs/ca-certificates.crt
  interface: 127.0.0.1
  access-control: 127.0.0.0/8 allow

forward-zone:
   name: "."
   forward-tls-upstream: yes

   forward-addr: 157.180.15.214@853#dns.envs.net
   forward-addr: 2a01:4f9:3100:3b2b:0:a:0:21@853#dns.envs.net
```
