the [gopher protocol](http://en.wikipedia.org/wiki/Gopher_(protocol)) was created in 1991. it didn't survive long due to [draconic licensing](http://www.nic.funet.fi/pub/vms/networking/gopher/gopher-software-licensing-policy.ancient).

we're trying to keep this cool corner of the web alive.

# # user gopher

main gopher page: `gopher://envs.net`

envs.net serves user gopherholes from your `~/public_gopher` directory.

to get listed on the [main gophermap](gopher://envs.net/),
make some changes to your root gophermap. the root gophermap
diffs against the default gophermap that was included with your account.

if a file called `gophermap` exists in the directory you're currently
browsing to in gopher, it will get processed and displayed.<br />
see [this example](https://github.com/gophernicus/gophernicus/blob/master/README.Gophermap) for more information on file types and special chars.

one of the coolest item types supported in gophernicus is `=` which allows you
to include other gophermaps or the output of executables.

you can even make your whole gophermap executable and it will be run through
whatever interpreter you specify in the shebang.

## browse gopher-sites
if you're currently connected from a envs.net shell, you can use the following browser.

- [`lynx`](https://lynx.browser.org/)
    - `lynx gopher://envs.net`
- [`vf1`](https://github.com/solderpunk/VF-1)
    - `vf1 gopher://envs.net`
- [`bombadillo`](https://tildegit.org/sloum/bombadillo)
    - `bombadillo gopher://envs.net`

if you want to access the gophersite in your public_gopher dir, use the following link structure:
&nbsp;&nbsp;`gopher://envs.net/1/~username`<br />
<br />
otherwise, you can use our [http proxy](https://gopher.envs.net/envs.net/) to browse the gophernet.
