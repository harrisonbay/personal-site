# Harrison Bay

Harrison's personal writing site, built with [Hugo](https://gohugo.io/) and the
[Shibui](https://github.com/ntk148v/shibui) theme. Cloudflare Pages builds and
publishes the site whenever `main` is updated.

## Write a post

1. Create a draft:

   ```sh
   hugo new content posts/my-post.md
   ```

2. Write in Markdown, then set `draft = false` in the post's front matter.

3. Preview it locally:

   ```sh
   hugo server -D
   ```

   The browser refreshes as you save. In VS Code, you can also press `Cmd+K V`
   to open the built-in Markdown preview beside the editor. For the exact
   Shibui layout, use the Hugo browser preview.

4. Publish it:

   ```sh
   git add content/posts/my-post.md
   git commit -m "Publish my post"
   git push
   ```

## Build

```sh
git submodule update --init --recursive
hugo --gc --minify --cacheDir "$PWD/.cache"
```

The generated static site is written to `public/`.

## Cloudflare Pages

- Production branch: `main`
- Build command: `hugo --gc --minify --cacheDir "$PWD/.cache"`
- Build output directory: `public`
- Environment variable: `HUGO_VERSION=0.165.0`

## VS Code shortcut

Run **Tasks: Run Task** from the Command Palette, then choose
**Hugo: Preview drafts**. It starts the local site and opens it in your browser.
