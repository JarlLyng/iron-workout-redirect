# Iron Workout redirect

Iron Workout is now [Anvil Workout](https://anvilworkout.iamjarl.com). This repo keeps the old
address, ironworkout.iamjarl.com, working by sending every visitor on to anvilworkout.iamjarl.com.

<p>
  <a href="https://madebyhuman.iamjarl.com"><picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://madebyhuman.iamjarl.com/badges/co-created-white.svg">
    <img src="https://madebyhuman.iamjarl.com/badges/co-created-black.svg" alt="Co-created with AI" width="120" height="40"></picture></a>
</p>

## How it forwards

GitHub Pages serves the `docs/` folder from `main` on the old domain, which is set in
`docs/CNAME`. The site is static, so there is no server redirect and no 301. The forward happens
in the browser.

`docs/index.html` answers the front page with a 200. A script sends the browser to the same path
on anvilworkout.iamjarl.com and keeps the query and the fragment. A meta refresh to the new front
page is there for a browser without JavaScript, and a canonical link points search engines at the
new site.

`docs/404.html` is the same file. GitHub Pages serves it with a 404 for every other path, and the
script forwards it the same way, so `/privacy` lands on `/privacy`. Without JavaScript a deep link
ends on the new front page.

Both pages show a short note with a link to the new site, in case the forward doesn't happen.

## Changing it

Keep `docs/index.html` and `docs/404.html` identical, and change them together. A push to `main`
publishes the change.

The app itself lives in [JarlLyng/Anvil-Workout](https://github.com/JarlLyng/Anvil-Workout).

## License

[MIT](LICENSE). It covers the code, not the Anvil Workout name or brand.
