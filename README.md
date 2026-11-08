# Kosatka themes

The catalog of themes for [Kosatka](https://github.com/kosatka-cms/kosatka):
a list of the themes' repositories (`themes.txt`), built every day into
<https://kosatka-cms.github.io/themes/index.json> - the engine's default
`themes_catalog_url`. Sites see it on *Appearance* and with
`app theme search`; a theme is installed from its own repository with
`app theme add`.

Each theme lives in a repository of its own; this one only lists them.

## The themes

### [C64](https://github.com/kosatka-cms/kosatka-theme-c64)

[![C64](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-c64/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-c64)

The Commodore 64's screen - the boot message, the main menu as a BASIC
listing, PETSCII frames in the machine's sixteen colours.

`retro` `dark` `pixel` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-c64
```

### [Galley](https://github.com/kosatka-cms/kosatka-theme-galley)

[![Galley](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-galley/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-galley)

A blog set like a printed page - a reading column and a margin with the
blocks, the byline and the contents, the site's name as a wordmark, rules
instead of cards, an accent colour, a light and a dark scheme.

`light` `dark` `serif` `blog` `typographic` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-galley
```

### [Harbor](https://github.com/kosatka-cms/kosatka-theme-harbor)

[![Harbor](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-harbor/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-harbor)

A classic blog of cards and a sidebar - the pinned item as a wide card,
the others in two columns, the sidebar's blocks as cards, the contents
of a long text beside it, a dark footer in columns, an accent colour, a
light and a dark scheme.

`light` `dark` `cards` `blog` `sidebar` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-harbor
```

### [Keel](https://github.com/kosatka-cms/kosatka-theme-keel)

[![Keel](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-keel/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-keel)

A company's site - a front page of bands (a hero, a dark band with
figures, bands in white and grey, a call to action with a form), each
made of blocks; services and projects as cards, the team, quotes from
clients; an accent colour. Comes with a demo site.

`light` `business` `company` `landing` `cards` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-keel
```

### [Respawn](https://github.com/kosatka-cms/kosatka-theme-respawn)

[![Respawn](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-respawn/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-respawn)

A light portal of news and reviews - a white header with the menu and a
search, cards on light grey, a list field's options as coloured badges,
a dark footer.

`light` `cards` `portal` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-respawn
```

### [Terminal](https://github.com/kosatka-cms/kosatka-theme-terminal)

[![Terminal](https://raw.githubusercontent.com/kosatka-cms/kosatka-theme-terminal/main/static/screenshot.jpg)](https://github.com/kosatka-cms/kosatka-theme-terminal)

A technical blog in a terminal - a prompt in the header, monospace
headings and dates, code blocks with highlighting and a copy button, the
contents of a long text, colour palettes, a dark and a light scheme.

`dark` `light` `monospace` `blog` `responsive`

```bash
app theme add https://github.com/kosatka-cms/kosatka-theme-terminal
```

Then commit `themes/` and choose the theme on *Appearance*. Each theme's
README has its settings.

## Adding a theme

1. Make sure the theme meets the requirements below and has a release (a
   tag `vX.Y.Z`).
2. Fork this repository and add the theme's repository address to
   `themes.txt`, in alphabetical order, and the theme to *The themes*
   above, in the same order: its name, screenshot, description, tags and
   install command, as the others.
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
