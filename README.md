# andeggs.me

Source for [www.andeggs.me](https://www.andeggs.me), the personal site of Francis Bacon. It's a [Jekyll](https://jekyllrb.com/) site using the [Minima](https://github.com/jekyll/minima) theme (version 2.5), with its own fonts and styling, built and hosted by GitHub Pages.

## Layout

| Path | What it is |
| --- | --- |
| `_config.yml` | Site title, URL, theme and plugins |
| `index.md` | Home page: a header image, then the list of posts |
| `about.md` | About page with profile photo, served at `/about/` |
| `_posts/` | Blog posts, named `YYYY-MM-DD-title.md` |
| `assets/main.scss` | Site stylesheet: loads the fonts, sets Minima's variables and adds custom styles |
| `assets/fonts/` | Self-hosted web fonts (Faustina, Inter) |
| `assets/images/` | Images used on the pages |
| `CNAME` | Custom domain (`www.andeggs.me`) for GitHub Pages |
| `Gemfile`, `Gemfile.lock` | Ruby gems, pinned to the versions GitHub Pages uses |
| `.devcontainer/` | Codespaces / dev container setup |

## Writing a post

Add a Markdown file to `_posts/` named `YYYY-MM-DD-title.md`, starting with:

```markdown
---
layout: post
title: "Your title"
---
```

Posts with a future date aren't published until that date.

## Changing the styling

All custom styling lives in [assets/main.scss](assets/main.scss), in this order:

1. `@font-face` rules for the fonts in `assets/fonts/`.
2. Minima variables such as `$base-font-family` and `$base-font-size`. These must come **before** `@import "minima"`.
3. `@import "minima"`.
4. Custom rules that override the theme, such as `.profile-image` for the round photo on the About page. These must come **after** the import.

Keep the empty `---` front matter lines at the top of the file. Jekyll only turns the file into CSS when they're there.

## Preview in GitHub Codespaces

The repo includes a dev container, so a Codespace comes with Ruby, Jekyll and the site's gems already installed.

1. On the repo's GitHub page, click **Code** → **Codespaces** → **Create codespace on main**.
2. Wait for the Codespace to finish setting up. `bundle install` runs automatically on first start.
3. In the Codespace terminal, start the site:

   ```sh
   bundle exec jekyll serve --livereload
   ```

4. When the "Your application running on port 4000 is available" notification appears, click **Open in Browser**. You can also open the **Ports** tab, find port 4000 and click the globe icon.

Jekyll rebuilds the site whenever you save a file. If the page doesn't refresh on its own, reload the browser tab. Changes to `_config.yml` are the exception: stop the server with `Ctrl+C` and start it again to pick them up.

Press `Ctrl+C` in the terminal to stop the server. Stop or delete the Codespace from [github.com/codespaces](https://github.com/codespaces) when you're done so it doesn't use up your included hours.

## Preview locally

With Ruby and Bundler installed:

```sh
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>.

## Publishing

Push to `main`. GitHub Pages builds and deploys the site automatically.
