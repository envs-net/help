the [gemini protocol](gemini://gemini.circumlunar.space) ([http proxy](https://gemini.envs.net/x/gemini.circumlunar.space)) was created in 2019.

gemini is a new internet protocol which:

- is heavier than gopher
- is lighter than the web
- will not replace either
- strives for maximum power to weight ratio
- takes user privacy very seriously


we're trying to keep this cool corner of the web alive.

# # user gemini

main gemini page: `gemini://envs.net`

envs.net serves user gemini sites from your `~/public_gemini` directory.

if a file called `index.gmi` exists in the directory you're currently browsing to in gemini, it will get processed and displayed.<br />
see [this example](gemini://gemini.circumlunar.space/docs/specification.gmi) ([http proxy](https://gemini.envs.net/x/gemini.circumlunar.space/docs/specification.gmi)) for more information on file types and special chars.

## browse gemini-sites
if you're currently connected from a envs.net shell, you can use the following browser.

- [`amfora`](https://github.com/makeworld-the-better-one/amfora)
	- `amfora gemini://envs.net`
- [`av98`](https://tildegit.org/solderpunk/AV-98)
    - `av98 gemini://envs.net`
- [`bombadillo`](https://tildegit.org/sloum/bombadillo)
    - `bombadillo gemini://envs.net`

if you want to access the gemini site in your public_gemini dir, use the following link structure:<br />
&nbsp;&nbsp;`gemini://envs.net/~username`<br />
<br />
otherwise, you can use our [http proxy](https://gemini.envs.net/) to browse the gemini-net.
