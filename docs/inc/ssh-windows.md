# ssh - windows usage

## windows 10

windows 10 1809 or later has openssh built in, so you no longer need to install third-party tools. if openssh is not enabled, please see microsoft's documentation on [openssh in windows](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_overview).

### generating your keypair

* open your new shell

* create your .ssh directory

```powershell
mkdir .ssh
```

* create your keypair

for ed25519 keys:

```powershell
ssh-keygen -t ed25519 -a 100
```

for rsa keys:

```powershell
ssh-keygen -t rsa -b 4096
```

* if you press enter to accept the defaults, your public and private key will
be located at `%UserProfile%\.ssh\id_ed25519.pub` and `%UserProfile%\.ssh\id_ed25519` respectively (or
`%UserProfile%\.ssh\id_rsa.pub` and `%UserProfile$\.ssh\id_rsa` if you chose rsa type)

* `type %UserProfile%\.ssh\id_ed25519.pub` (or `type %UserProfile%\.ssh\id_rsa.pub` for rsa)

* copy the output of the last command and paste it in the sshkey field on the signup form.

### using your keypair

* open powershell (right click start button and select "windows powershell")

* `ssh` to envs.net:

```bash
ssh username@envs.net
```

---

## legacy windows

older versions of windows unfortunately do not come with openssh, and you will need to install a third-party tool. you may choose from any of the following options:

- [windows subsystem for linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
- [msys2](http://www.msys2.org/)
- [git bash](https://git-scm.com)

* open your new shell

* create your .ssh directory

```bash
mkdir .ssh
```

* create your keypair

for ed25519 keys:

```bash
ssh-keygen -t ed25519 -a 100
```

for rsa keys:

```bash
ssh-keygen -t rsa -b 4096
```

* if you press enter to accept the defaults, your public and private key will
be located at `~/.ssh/id_ed25519.pub` and `~/.ssh/id_ed25519` respectively (or
`~/.ssh/id_rsa.pub` and `~/.ssh/id_rsa` if you chose rsa type)

* `cat ~/.ssh/id_ed25519.pub` (or `cat ~/.ssh/id_rsa.pub` for rsa)

* copy the output of the last command and paste it in the sshkey field on the signup form.

### using your keypair

* open terminal (location will vary depending on your choice)

* `ssh` to envs.net:

```bash
ssh username@envs.net
```
