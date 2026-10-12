# andeggs.me

Source for [www.andeggs.me](https://www.andeggs.me), the personal site of Francis Bacon. It's a [Jekyll](https://jekyllrb.com/) site using the [Minima](https://github.com/jekyll/minima) theme, built and hosted by GitHub Pages.

## Layout

| Path | What it is |
| --- | --- |
| `_config.yml` | Site title, description, theme and plugins |
| `index.md` | Home page (lists posts) |
| `about.md` | About page, served at `/about/` |
| `_posts/` | Blog posts, named `YYYY-MM-DD-title.md` |
| `.devcontainer/` | Codespaces / dev container setup |

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
