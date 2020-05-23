# ssh - mac usage

## generating your keypair

1. open terminal (it's in `/Applications/Utilities`)

2. create your .ssh directory:

```bash
mkdir -m 700 ~/.ssh
```

3. create your keys:

for dd25519 keys:

```bash
ssh-keygen -t ed25519 -a 100
```

for rsa keys:

```bash
ssh-keygen -t rsa -b 4096
```

4. if you press enter to accept the defaults, your public and private key will
be located at `~/.ssh/id_ed25519.pub` and `~/.ssh/id_ed25519` respectively (or
`~/.ssh/id_rsa.pub` and `~/.ssh/id_rsa` if you chose rsa type)

5. `cat ~/.ssh/id_ed25519.pub` (or `cat ~/.ssh/id_rsa.pub` for rsa)

6. copy the output of the last command and paste it in the sshkey field on the signup form.

## using your keypair

7. open terminal (it's in `/Applications/Utilities`)

8. `ssh` to envs.net:

```bash
ssh username@envs.net
```
