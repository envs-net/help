# GPG/OpenPGP WKD (Web Key Directory) for envs.net email
*user script by [~dan](https://dan.envs.net/)*

You can make your GPG/OpenPGP public key available on the envs.net WKD service for automatic download into many Email clients, which support this standard.

## Generate a GPG key pair for your email
There is a good [Youtube Tutorial](https://www.youtube.com/watch?v=1vVIpIvboSg) for creating a key pair. I would recomment the recent defaults. The  only reason to use the `gpg --full-gen-key` command instead of the simpler `gpg --gen-key` is, that you can add a comment to your key. But you should go with the defaults however. And be sure to enter the right email address: `username@envs.net`.

## Export your public key
After you created your key-pair, it's time to export your public key on your local machine (where you generated the key-pair). This is done with the following command: `gpg --export --armour --fingerprint username@envs.net > ~/public_key.gpg`

Now you've exported your public key to your home directory named `~/public_key.gpg`.

## Upload your public key
To make your key available to the envs.net WKD service, you need to upload it to your shell account with the name `~/.public_key.gpg` (notice the dot infront of the filename). This is done with the following command: `scp ~/public_key.gpg username@envs.net:~/.public_key.gpg`. That's it, although your key isn't available immediately.

## System cron job to update your uploaded key
All the key files in all the users directorys ( `~/.public_key.gpg` ) are uploaded to the WKD service with a system cron job run every 12 hours. So you may need to wait some time until it gets available. The same goes, when you update or change your key.

## Check, if your key is reachable over WKD
You can check the availability of your public key on the WKD service on this website: [https://www.webkeydirectory.com/](https://www.webkeydirectory.com/). Just enter your email address `username@envs.net`, and it will check, if it's correctly set up.

**But remember**: It can take up to 12 hours until your key gets  available to the WKD service of envs.net.

## Setting up GnuPG to use WKD for receiving other peoples public keys
If you want to automatically receive the keys of your recipients with GnuPG, you have to add the following option to your local `~/.gnupg/gpg.conf` file:  

```
auto-key-locate dane,cert,wkd,keyserver
keyserver hkps://keys.openpgp.org/
trust-model tofu+pgp
```

Now your gpg client is able to fetch the public keys of your repicients if they are available at all. It will also use different methods to fetch a recipients public key additionally, for example querying the keys.openpgp.org server for a key.

## Help
You can get help for setting up your public key by writing your issue to the main mailing list [team@envs.net](mailto:team@envs.net) or on our XMPP server in the [envs](xmpp:envs@conference.envs.net?join) room on `conference.envs.net`.

If you have security concerns, contact [dan@envs.net](mailto:dan@envs.net) via email or contact the admin [creme@envs.net](mailto:creme@envs.net) directly.

# Security
**Be careful and responsible!**

Never ever  create a key for an email address of another envs.net user! The update script (cron job) *will* recognize this and *will* exclude your key from being added to the WKD. Violating this rule will result in a permanent ban from your shell and mail account on envs.net, unless this happened by accident.

# Conclusion
If all goes well, people wanting to send you an encrypted email should be able to receive your public key automatically, if their clients supports WKD.

Please understand, that we can't always give help for every email client out there.

But WKD gets broader reception more and more, so there shoud be more and more email clients supporting WKD. Personally I've set up NeoMutt to use GnuPG with WKD and as far as I know, Thunderbird (maybe with the 'enigma' plugin) also supports WKD.

If you know of any email client supporting WKD, please let us know and we will maybe maintain a list of them.
