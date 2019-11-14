# # user website
you're user page is available under

*https://envs.net/~username/*, *https://envs.net/u/username/*,<br />
*https://username.envs.net/* and *https://username.envs.sh/*.

the index file location for our page is `~/public_html/` and<br />
a template for the page can you found in `~/public_html/your_index_template.php`.

static files are served normally, along with the following dynamic options:

- php - name the file with a `php` extension or use index.php
- sh / cgi - name the file with a `sh` or `cgi` extension
- perl - name the file with a `pl` extension
- python - name the file with a `py` extension
- lua - name the file with a `lua` extension
- cgi-bin - name it whatever you want and place it in `~/public_html/cgi-bin/`

if you're having trouble with any of these cgi scripts, make sure that the script has<br />
a correct shebang, sending the content-type header as the first thing and<br />
don't forget to make the scripts executable.

also you can use 'ssi' (server-side-includes). make sure you do not use a leading `/`.<br />
example: `<!--#include virtual="cgi-bin/fortune.sh" -->`

### ssgs

- [mkdocs](https://www.mkdocs.org/) - markdown project documentation tool.
additional themes are available from the [mkdocs-bootstrap](
http://mkdocs.github.io/mkdocs-bootstrap/) and [mkdocs-bootswatch](
http://mkdocs.github.io/mkdocs-bootswatch/) projects. just set your theme name
to one those listed and rebuild. generally recommended to not build the mkdocs
source directly in your webroot. set the destination to somewhere in `~/public_html`,
symlink, or move/copy the generated files manually. for example, if you wanted to
make a mkdocs site called mywiki available on the web, you could do:
`ln -s ~/mywiki ~/public_html/wiki`
- [hugo](https://gohugo.io/) - static site generator built in go
- [jekyll](https://jekyllrb.com/) - static site generator used by github for
[github pages](https://pages.github.com) built in ruby
- [pelican](https://getpelican.com/) - pelican is a static site generator, written in python
- [zola](https://www.getzola.org/) - single-binary static site generator written in rust

## forward / rewrite url to a other site

If you would like to redirect your page then you can do so with a simple workaround.

example `index.html`:
```html
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="refresh" content="0; url=https://www.w3docs.com/" />
  </head>
</html>
```
example `index.php`:
```php
<?php
  header('Location: https://www.w3docs.com/', true, 301);
  exit();
?>
```
