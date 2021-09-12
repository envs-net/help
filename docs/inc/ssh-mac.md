# ssh - mac usage

## generating your keypair

* open a terminal (it's in `/Applications/Utilities`)

* create your .ssh directory:

```bash
mkdir -m 700 ~/.ssh
```

* create your keys:

for dd25519 keys:

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

## using your keypair

* open a terminal (it's in `/Applications/Utilities`)

* `ssh` to envs.net:

```bash
ssh username@envs.net
```
