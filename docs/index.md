# envs.net ~ help page

[https://envs.net | environments](https://envs.net) - *since 9/2019*

> *write on matrix [`#envs:envs.net`](https://matrix.to/#/#envs:envs.net)*<br />
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
  [blog](https://help.envs.net/blog/) /
  [databases](https://help.envs.net/database/) /
  [gopher](https://help.envs.net/gopher/) /
  [gemini](https://help.envs.net/gemini/) /
  [finger](https://help.envs.net/finger/) /
  and much more ..

## services
create an account on any of these services as you like.

### # code related stuff
- [gitea](https://git.envs.net/) - git with a cup of tea. - lightweight code hosting solution.  
members can be use your email credantials for login. (*username@envs.net* | *your email pw*)
- [drone](https://drone.envs.net/) - drone is a container-native, continuous delivery platform.  
(includes a "drone-ssh-runner" and "drone-docker-runner".)

### # general utilities
- [searxng](https://searx.envs.net/) - privacy-respecting metasearch engine
- [nullpointer (0x0)](https://envs.sh) - file hosting and url shortener
- [privatebin](https://pb.envs.net/) - pastebin service
- [hedgedoc](https://hedgedoc.envs.net/) - collaborative real time markdown
- [cryptpad](https://pad.envs.net/) - collaborative real time editing
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
- [ffsync](https://help.envs.net/tutorials/ffsync/) - firefox sync server
- [tt-rss](https://rss.envs.net/) - news feed reader and aggregator
- [ip address info](https://ip.envs.net/)

### # social / communications
- [bbj](https://bbj.envs.net/) - forum
- [email](https://mail.envs.net/) - webmail
- [mailing lists](https://lists.envs.net/) - list archives are available [on the web here](https://lists.envs.net/hyperkitty/).
<br /><br />
- [gopher proxy](https://gopher.envs.net/) - defaults to our local gopher: `gopher://envs.net`<br />(on port 70)
- [gemini proxy](https://gemini.envs.net/) - defaults to our local gemini: `gemini://envs.net`<br />(on port 1965)
<br /><br />
- [getwtxt](https://twtxt.envs.net/) - microblogging for hackers - twtxt registry - see [twtxt](https://help.envs.net/blog/#with-twtxt) help page for more infos.
- [pleroma](https://pleroma.envs.net/) - microblogging - federated social network - _[what is pleroma?](https://blog.soykaf.com/post/what-is-pleroma/)_
- [mobilizon](https://mobilizon.envs.net/) - manage your events - gather, organize and mobilize
<br /><br />
- [matrix](https://envs.net/chat/matrix/) - secure, decentralised, real-time communication.
    - [matrix-help.envs.net](https://matrix-help.envs.net/) - help & documentation about matrix/element at envs.net
    - [element-web](https://element.envs.net/) - element-web client for matrix. audio- and video calls are also possible in this.
    - [hydrogen-web](https://hydrogen.envs.net/) - lightweight matrix client with legacy and mobile browser support.
    - [cinny](https://cinny.envs.net/) - cinny is a matrix client focusing primarily on simple, elegant and secure interface.
    - [dimension](https://dimension.envs.net/) - an open source integrations manager for matrix clients, like element.

- [irc](https://envs.net/chat/irc/) - irc network for the tildeverse
- [thelounge](https://webirc.envs.net/) - irc webclient - runs in private mode: it stays connected for you. run `webirc` to create a login.
- [znc](https://znc.envs.net/) - irc bouncer - log in with your `username` and email password and configure as needed.

### # public dns-server

**host:** `dns.envs.net`  
**ip:** `5.199.130.141`  
**port:** `53`

#### dns-over-tls (dot)

**host:** `dns.envs.net`  
**ip:** `5.199.130.141`  
**port:** `853`  
**tls_pubkey_pinset:** `TknTKtNi/lhE270MszuUQlgqk1HnGcUXFAgXSXURD7k=` _(**digest:** `sha256`)_

##### example unbound config  (`/etc/unbound/unbound.conf`)
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

   forward-addr: 5.199.130.141@853#dns.envs.net
```
