# Kosatka themes

The catalog of themes for [Kosatka](https://github.com/kosatka-cms/kosatka):
a list of the themes' repositories (`themes.txt`), built every day into
<https://kosatka-cms.github.io/themes/index.json> - the engine's default
`themes_catalog_url`. Sites see it on *Appearance* and with
`app theme search`; a theme is installed from its own repository with
`app theme add`.

Each theme lives in a repository of its own; this one only lists them.

## Adding a theme

1. Make sure the theme meets the requirements below and has a release (a
   tag `vX.Y.Z`).
2. Fork this repository and add the theme's repository address to
   `themes.txt`, in alphabetical order.
3. Open a pull request. Its check builds the catalog with your theme:
   a theme that can't be installed (no release, a broken `theme.yaml`)
   fails it.

## Requirements

- **The repository** is the theme's directory: `theme.yaml` at the root,
  `templates/`, `static/`, `translations/`. Name it `kosatka-theme-<name>`:
  sites install it into `themes/<name>/`.
- **Releases are tags** `vX.Y.Z`; `version` in `theme.yaml` is the
  release, `min_version` the oldest engine release the theme works with.
- **The manifest** has a `description`, an `author`, a `license`, `tags`
  and a `screenshot` (`static/screenshot.jpg`) - the catalog and the
  *Appearance* page show them.
- **An open-source license.** No paid themes; a fork must differ notably
  from the original and keep its license.
- **A README in English**, with an absolute link to the screenshot.
- **No third-party CDNs, trackers or analytics**, no copyrighted images.
- **The engine's regions** where they fit, so blocks stay in place when a
  site switches themes.

See [Distributing a theme](https://kosatka-cms.github.io/kosatka/themes/distribute/)
in the engine's documentation.

A theme that hasn't had a release for 18 months, or that no longer works
with the engine's current release, may be removed from the list.

## Building locally

With the engine's binary:

```bash
app theme index -list themes.txt -out dist/index.json
```

or `go run github.com/kosatka-cms/kosatka/cmd/app@main theme index -list themes.txt -out dist/index.json`.
`GITHUB_TOKEN` raises GitHub's limit of anonymous requests (the stars and
the last push of each theme).

## License

MIT
