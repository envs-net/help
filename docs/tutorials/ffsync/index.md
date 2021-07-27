# envs's firefox sync server

**url: `https://ffsync.envs.net/`**

## client configuration

if you are logged into firefox with your firefox account, log out!

### desktop

to configure desktop firefox to talk to our sync server, go to `about:config`, search for `identity.sync.tokenserver.uri` and change its value to be the url of our server with a path of `token/1.0/sync/1.5`:

`identity.sync.tokenserver.uri: https://ffsync.envs.net/token/1.0/sync/1.5`

### android

firefox for android ("daylight", versions 79 and later) does support using a non-mozilla-hosted sync server.
go to "App Menu > Settings > About Firefox" and click the logo 5 times. you should see a "debug menu enabled" notification. go back to the main menu and you will see two options for a custom account server and a custom sync server. set the sync server to the 
url: `https://ffsync.envs.net/token/1.0/sync/1.5`
and then log in.

to configure android firefox 44 up to 78 to talk to our sync server, just set the "identity.sync.tokenserver.uri" exactly as above before signing in to firefox accounts and sync on your android device.

**important:** after creating the android account, changes to "identity.sync.tokenserver.uri" will be ignored. (if you need to change the uri, delete the android account using the "Settings > Sync > Disconnect…" menu item, update the pref, and sign in again.) non-default tokenserver url's are displayed in the "Settings > Sync" panel in firefox for android, so you should be able to verify your url there.

prior to firefox 44, a custom add-on was needed to configure firefox for android. for firefox 43 and earlier, see the blog post [how to connect firefox for android to self-hosted firefox account and firefox sync servers](http://www.ncalexander.net/blog/2014/07/05/how-to-connect-firefox-for-android-to-self-hosted-services/).
