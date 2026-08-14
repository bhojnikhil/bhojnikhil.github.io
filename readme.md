# bhojnikhil.github.io

Personal site for Nikhil Bhoj — Senior Software Engineer (payments, data, and ML systems for
healthcare & fintech). Live at <https://bhojnikhil.github.io>.

Static HTML served by GitHub Pages. Built on the
[Start Bootstrap "Agency"](https://startbootstrap.com/template-overviews/agency) template (MIT).

## Layout

| Path | What it is |
| --- | --- |
| `index.html` | The entire site — one page, edit this for content changes |
| `Nikhil_Bhoj_Resume.pdf` | Resume, linked from the nav and the contact section |
| `scss/` | Style sources |
| `css/agency.css`, `css/agency.min.css` | Compiled styles — what the page actually loads |
| `js/agency.js`, `js/agency.min.js` | Nav shrink + smooth scrolling |
| `vendor/` | Bootstrap 4, jQuery, Font Awesome (committed, not installed) |

Content-only edits just need `index.html`. Nothing to build, nothing to install — push to
`master` and Pages picks it up.

## Styles

The original `gulp` pipeline no longer runs (`gulp-sass` 4 pins `node-sass`, which won't build
on current Node). Until it's replaced, **`scss/` and the two `css/` files are kept in sync by
hand** — change a rule in `scss/`, make the matching change in `css/agency.css` and
`css/agency.min.css`. Same for `js/agency.js` / `js/agency.min.js`.

A full recompile is possible with dart-sass:

```sh
npx sass scss/agency.scss css/agency.css --style=expanded --no-source-map
```

but note it drops the autoprefixer vendor prefixes currently in the file and rewrites `darken()`
output, so it is not a drop-in replacement.
