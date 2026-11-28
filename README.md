# ndexbio.github.io
Organization level github pages

## Home-page content: `contentrootpath/`

The NDEx home page loads its content from this folder, published at
<https://ndexbio.github.io/contentrootpath/>. NDEx finds it through
`uiContent.contentRootPath` in its `config.json`.

| File | What it controls |
|---|---|
| `featured_content.json` | The featured carousel at the top of the home page |
| `main.json` | The panels below the carousel. Each entry names an HTML file in this folder. |
| `logos.json` | The logo carousel |
| `featured_networks.json` | Not shown by NDEx3 at present |
| `img/`, `logos/` | Images used by the files above |

To change the home page, edit these files on GitHub, either directly or in a pull
request. The site republishes about a minute after a change reaches `main`. Visitors
may not see it for up to 10 minutes because of caching.

Rules for this folder:

- **Use full URLs for images** in `featured_content.json` and in the HTML panels,
  for example `https://ndexbio.github.io/contentrootpath/img/name.png`. The HTML is
  inserted into the NDEx page, so a relative path would point at NDEx's own address.
  The `image` paths in `logos.json` are the exception: NDEx adds the folder URL to
  them, so they stay relative (`logos/name.png`).
- **Review HTML changes as you would code.** The panels run unchanged on
  www.ndexbio.org, including any inline `onclick` handlers.
- **Don't add a `README.md` or `index.html` to `contentrootpath/`.** The folder's own
  URL returns 404. Either of those files would be shown there instead. Keep notes in
  this file.
- **Don't add `.nojekyll` to this repo.** Jekyll is what turns `legal.md` into the
  legal page. Jekyll copies the JSON, HTML and image files unchanged, as long as they
  don't start with `---` and their names don't start with `_` or `.`.
