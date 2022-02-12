# basic help

> *write on matrix [`#envs:envs.net`](https://matrix.to/#/#envs:envs.net)*  
> *for any help requests and community support.*

## # show public ip
`curl ip.envs.net`

## # the null pointer - aliases
add the following lines to your aliases file `~/.bash_aliases`
```bash
0file() { curl -F"file=@$1" https://envs.sh ; }
0pb() { curl -F"file=@-;" https://envs.sh ; }
0url() { curl -F"url=$1" https://envs.sh ; }
0short() { curl -F"shorten=$1" https://envs.sh ; }
```
HTTP POST files here:  
&nbsp;&nbsp;`0file "yourfile.png"`

post your text directly:  
&nbsp;&nbsp;`echo "text here" | 0pb`

you can also POST remote URLs:  
&nbsp;&nbsp;`0url "https://example.com/image.jpg"`

or you can shorten URLs:  
&nbsp;&nbsp;`0short "https://example.com/some/long/url"`

!!! tip
    if you want a nice wrapper, try [~tomasino's pb](https://git.envs.net/envs/pb)

## # ssh
your ssh directory is: `~/.ssh/`, which includes the following files:

- your ssh config file `~/.ssh/config` (more below)
- the `authorized_keys`, this file is a list of public keys (one per line) that are allowed to log in to your user account.
- `id_ed25519` or `id_rsa` are each private keys, and `id_ed25519.pub` or `id_rsa.pub` are the corresponding pubkey.

### sshfp

| Algorithm | Fingerprint |
| --- | --- |
| RSA       | `SHA256:7dB470mfzlyhhtqmjnXciIxp+jWLACiYKC3EE/Z0lFg` |
| ECDSA     | `SHA256:U0C6SKGXUflve16m2l4KWBdLLARW6O8TiGWZsXAU2i4` |
| ED25519   | `SHA256:V+mXTsRJ+jfJMxxPlD/28dpWouuns3Wuqwppv6ykVC8` |

the key fingerprints are in dns as sshfp records as well, which you can check against  
by setting VerifyHostKeyDNS to yes in your `~/.ssh/config`.

you can check the records yourself with the `dig` tool like this:  
&nbsp;&nbsp;`dig sshfp envs.net`

### ssh details and usage
ports 22, 80, 443, 2222 and 2223 are available for ssh  
use ssh.envs.net to reach the secondary ip and use 80 and 443 for ssh.  
so, for example, you can do:  
&nbsp;&nbsp;`ssh user@envs.net` 
&nbsp;&nbsp;`ssh -p2223 user@envs.net`

or for the secondary ip:
&nbsp;&nbsp;`ssh -p443 user@ssh.envs.net`

!!! tip
    if you have a slightly shaky connection then you can also use `mosh`.

***

&gt; [ssh windows usage](inc/ssh-windows.md)
&gt; [ssh mac usage](inc/ssh-mac.md)

***

### create a ssh-key
make sure you have a `~/.ssh directory`  
&nbsp;&nbsp;`mkdir -m 700 ~/.ssh`

create your key  
&nbsp;&nbsp;`ssh-keygen -t ed25519 -a 100`

your public and private key will be located at  
&nbsp;&nbsp;`cat ~/.ssh/id_ed25519.pub`

you can also use rsa:  
&nbsp;&nbsp;`ssh-keygen -t rsa -b 4096`  
&nbsp;&nbsp;`cat ~/.ssh/id_rsa.pub`

### ssh config
define ssh host aliase in `~/.ssh/config`
```bash
Host envs.net
  HostName envs.net
  Port 2223
  User user
  LocalForward localhost:6667 localhost:6667
```

now you can use a simple `ssh envs.net` to connect.  
there are tons of other options, including this `LocalForward` line to automatically set up the tunnel as show below.  
for more available options, see the man page: `man ssh_config`

### ssh tunnels
for example, you want to get into znc with your local client (weechat, etc),  
but your local network blocks znc ports. you can connect to envs.net, and use port forwarding to get on.

if you are connecting from a linux machine, you can do this:  
&nbsp;&nbsp;`ssh -L 6667:localhost:6667 envs.net`

after being logged in, open your local irc client, and use  
&nbsp;&nbsp; `127.0.0.1:6667`  
for your server setting. voila! you're now on envs.net znc server.  

what that ssh command did was open a local port tunnel (-L), using local port 6667 (6667:)  
pointed at localhost (from the remote's point of view), on remote port 6667 (default irc port).

putty has the same ability (for windows and mac users), under connection &gt; ssh &gt; tunnels.

you can do this for any arbitrary port.

### import &amp; authorize a public ssh-key
from URL (on remote machine)  
&nbsp;&nbsp;`echo $(curl -sL https://example.com/id_rsa.pub) | tee -a ~/.ssh/authorized_keys`

over ssh (on local machine)  
&nbsp;&nbsp;`ssh-copy-id -i ~/.ssh/id_rsa.pub -p2223 user@envs.net;`

### ssh remote execution
`ssh envs.net ping google.de`

or  
&nbsp;&nbsp;`ssh envs.net bash -c "'uname -a'"`

exec a local script  
&nbsp;&nbsp;`ssh envs.net 'bash -s' < local_script.sh`

## # scp usage
copy ssh pub key to remote:  
&nbsp;&nbsp;`scp -P 2223 ~/.ssh/authorized_keys user@envs.net:~/.ssh/authorized_keys`

copy website index.html from remote:  
&nbsp;&nbsp;`scp -P 2223 user@envs.net:~/public_www/index.html ~/public_www/`

## # rsync usage
sync website to remote:  
&nbsp;&nbsp;`rsync -avz -e "ssh -p 2223" ~/public_www user@envs.net:~`  
sync website from remote:  
&nbsp;&nbsp;`rsync -avz -e "ssh -p 2223" user@envs.net:~/public_www ~/`

## # sftp usage
connect: `sftp -oPort=2223 user@envs.net`

### commands:
exit:	`exit`  
print help:	`help`

### transferring
files to remote:  
&nbsp;&nbsp;`put localfile remotefile`

dir to remote:  
&nbsp;&nbsp;`put -r localdir remotedir`

files from remote:  
&nbsp;&nbsp;`get remotefile localfile`

dir from remote:  
&nbsp;&nbsp;`get -r remotedir localdir`

### example:
add index.html to public_www Dir:  
&nbsp;&nbsp;`put public_www/index.html public_www`

add `~/.ssh/authorized_keys:`
&nbsp;&nbsp;`put .ssh/authorized_keys .ssh/authorized_keys`

### single line usage (on local machine)
&nbsp;&nbsp;to remote:   `sftp -P 2223 user@envs.net:remotedir <<< $'put localfile_path'`  
&nbsp;&nbsp;from remote: `sftp -P 2223 user@envs.net:remotefile localfile`

## # your shell
avaliable shells: `ash`, `bash`, `csh`, `dash`, `elvish`, `fish`, `ksh`, `mksh`, `sash`, `sh`, `tcsh`, `xonsh`, `yash`, `zsh`  
*list all available shells: `more /etc/shells`*

to change your shell use: `chsh -s $(which <shell>)`  
or `chsh -s <path_to_shell>`

example: `chsh -s $(which bash)` or `chsh -s /bin/bash`

### default byobu-session
familiar with tmux, continue as normal, but with ctrl-a instead of ctrl-b  
if you don't want to this happen by default when you log in, run `byobu-disable`.  

`man byobu` for more info.

press shift-f1 for a full list of keybinds  
f2 creates a new tab  
f3 and f4 move you between tabs  
f6 disconnects and leaves everything running  
shift-f12 disable/enable byobu f-key bindings

## # timezone
The timezone by default on the server is UTC.

If you want to make it so that your shell prints out dates in localtime for you,  
run `tzselect` to find the correct timezone name that you’ll need to export as the TZ environment variable.

for example, if you’re in eastern time, add something like this  
`export TZ="America/Detroit"`  
to your `~/.profile`.

to get your timezone you can use `date`.

## # scheduled activity
the linux utilities `cron` and `at` are related commands. you might use crontab, for example, to perform a task each morning at 2 a.m., and use at to remind yourself of an appointment later in the day.

### cron/crontab
the cron utility allows you to schedule a repetitive task to take place at any regular interval desired.  
for more information see the manual pages of crontab(5) and cron(8)

display current crontabs:  
&nbsp;&nbsp;`crontab -l`

add/edit crontabs:  
&nbsp;&nbsp;`crontab -e`

example: - backup your mysql db once per day
```bash
..
# NOTE: * To disable email notifications use:
#         - for single cronjobs use after the cmd: >/dev/null 2>&1
#         - comment out to disable all email alerts in the crontab:
#MAILTO=""
# m h	dom	mon	dow	command
0 	0	*	*	*	/usr/local/bin/envs_mysql.sh backup
```

### at
the at command lets you specify a one-time action to take place at some desired time.<br />
for more information see the manual page of at.

examples:
```bash
# schedule task to execute just after 1 hour.
echo 'sh myscript.sh' | at now + 1 hour
# schedule task at 10:00 AM on coming sunday.
echo 'sh myscript.sh' | at 10:00 AM Sun
# schedule task to execute at midnight.
echo 'sh myscript.sh' | at midnight
```

view your at queue:  
&nbsp;&nbsp;`at -l` or `atq`  
&nbsp;&nbsp;`2       Sun Dec 29 14:03:00 2019 a creme`

delete at job id 2:  
&nbsp;&nbsp;`at -r 2` or `atrm 2`

## # daemonize processes
so you've got a process that you want to keep running. you might have it in a  
tmux or screen session. let's use systemd user units to manage it!

- ensure that your user unit loadpath is set up:<br />`mkdir -p ~/.config/systemd/user/`
- create a basic service. save something like this<br />in `~/.config/systemd/user/my-new-service.service` (adjusting where necessary)
```bash
[Unit]
Description=my script description
[Service]
ExecStart=/bin/bash -c "while true do; echo hi; done"
[Install]
WantedBy=default.target
```
- enable it:<br>`systemctl --user enable --now my-new-service.service`
- enable-linger for your user account:<br />`loginctl enable-linger`<br />this allows your user units to run even when you're not logged in.

done!  
you can now use `systemctl --user` to manage your daemonized process.
