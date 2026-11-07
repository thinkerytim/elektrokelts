# The ElektroKelts — elektrokelts.com

Static one-page site for the band, hosted on GitHub Pages. No build step.

## Files

- `index.html` — all page content (show info, photos, video, booking email)
- `style.css` — styles (colors and fonts are set in the `:root` block at the top)
- `assets/img/` — logo files (`logo-light.svg` is the white-on-dark version used on the site, `logo-dark.svg` is black-on-light for print)
- `assets/photos/` — gallery photos
- `CNAME` — custom domain for GitHub Pages; leave as `elektrokelts.com`

## Updating the site

1. Edit `index.html` (or drop new photos into `assets/photos/` and add an `<a><img></a>` block to the `.gallery` div).
2. Commit and push to `main`. GitHub Pages redeploys in about a minute.

```bash
git add -A
git commit -m "Add fall show dates"
git push
```

## Adding a video

Facebook videos embed with the plugin URL. Replace the video ID in the `iframe` `src` in `index.html`:

```
https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2FElektroKelts%2Fvideos%2F<VIDEO_ID>%2F&show_text=false
```

Only public videos embed. YouTube embeds work too (`https://www.youtube.com/embed/<ID>`).

## DNS for elektrokelts.com

At the domain registrar, point the apex domain at GitHub Pages with four A records and add a CNAME for `www`:

```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
CNAME www  thinkerytim.github.io.
```

Then in the GitHub repo, Settings → Pages, confirm the custom domain and tick "Enforce HTTPS" once the certificate is issued.
