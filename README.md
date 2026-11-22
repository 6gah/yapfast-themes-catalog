# yapfast themes

the launch themes for [Yapfast](https://github.com/yapfast/yapfast) and the catalog its marketplace reads.

- `themes/<name>/` holds each theme: a `theme.json` plus the files it names
- `catalog.json` lists every theme at a pinned commit with the sha256 of its files, so what installs is exactly what was listed

## getting your theme listed

1. put your theme in a public github repo (the whole repo, or a folder in it)
2. run `yapfast theme check path/to/theme --marketplace`. it has to pass, and it prints the `sha256` for your entry
3. open a pull request here adding your entry to `catalog.json`:

```json
{
  "id": "io.github.you.mytheme",
  "name": "My Theme",
  "author": "you",
  "repo": "https://github.com/you/mytheme",
  "path": "",
  "commit": "the full commit hash your theme is at",
  "sha256": "what theme check printed",
  "description": "one or two lines",
  "preview": "https://raw.githubusercontent.com/you/mytheme/<commit>/previews/chat.webp",
  "light": true,
  "dark": false
}
```

`path` is the folder inside the repo, or empty if the theme is the whole repo. `id` must match your `theme.json`. a new version is a new pull request with the new commit and sha256.

## making a theme

`yapfast theme new mytheme` starts one from the template, and `yapfast --theme-dev mytheme` shows it live while you edit. the full guide is `docs/themes.md` in the yapfast repo.
