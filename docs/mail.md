# # user email
we use the [modoboa](https://modoboa.org/) mail-software on our server.

|  |  |  |
| ------------------------- |:---:|:---:|
| server-address:           | [mail.envs.net](https://mail.envs.net/) |  |
| username:                 | username@envs.net |  |
|  |  |
| smtp server-port:         | 587 | 465 |
| smtp connection-security: | STARTTLS | SSL/TLS |
|  |  |
| imap server-port:         | 143 | 993 |
| imap connection-security: | STARTTLS | SSL/TLS |
|  |  |
| pop server-port:          | 110 | 995 |
| pop connection-security:  | STARTTLS | SSL/TLS |

further mail settings such as password change and email forwarding can be found directly in your [webmail](https://mail.envs.net/user/#profile/).<br />
(*an secondary e-mail address, can be used for recovery needs.*)

managesieve is also supported and is available on the default port `4190`.

if you want to use an external managesieve client (like the [thunderbird add-on](https://github.com/thsmi/sieve)).<br />
you can also set up your filter in the [webmailer](https://mail.envs.net/sfilters/).

## GPG/OpenPGP WKD (Web Key Directory)

You can make your GPG/OpenPGP public key available on the envs.net WKD service for automatic download into many Email clients, which support this standard.  
more about at: [https://help.envs.net/user-wkd/](user-wkd.md)
