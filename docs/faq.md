# frequently asked questions

## Q: how do i sign-up for an account?
simply by going to our [sign-up page](https://envs.net/signup/) and filling in the form.

## Q: can i get password-based login?
no. sorry. not for shell access. for other integrated services, password auth will be enabled, but not for your ssh connection. we use key based authentication, as it's more secure, and more convienent for you, to be honest.

## Q: can i rename my account username?
no. sorry.

## Q: can i remove my account?
yes sure. please send us an email with your request to: [sudoers@envs.net](mailto:sudoers@envs.net).

## Q: how can i disable the default byobu-session?
if you don't want this to happen by default, when you log in to your shell, run `byobu-disable`.

## Q: can i get a package installed?
probably! send a message in our irc-channel #envs or an email with your suggestion to [sudoers@envs.net](mailto:sudoers@envs.net).

## Q: can i open the port for service i have running?
no. due to security issues, we cannot. however, you can certainly use an [ssh-tunnel](https://help.envs.net/help/#ssh-tunnels) to access it.

## Q: can i make my scripts available to other users?
yeah very much like. you can simply use `envs submit` in the shell to submit your script. :)<br />
with `envs list` you can display all userscripts.
