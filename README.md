<p align="center">
    <img src="https://d33wubrfki0l68.cloudfront.net/9a47dde680cca08e326c07824009ed1adc29626e/6a1c0/logo-title.png" width=30%/>
    <img src="https://avatars.githubusercontent.com/u/6506055?s=280&v=4" width=30%/>
</p>

# Asciinema player for Slidev

> Slidev addon to embed asciinema casts to presentations.

![demo](https://raw.githubusercontent.com/murilo-cunha/slidev-addon-asciinema/main/public/casts/demo.gif)

## Get started

### Create a project

With NPM:

```console
npm init slidev
```

With Yarn:

```console
yarn create slidev
```

With pnpm:

```console
pnpm create slidev
```

### Add slidev addon

With NPM:

```console
npm install slidev-addon-asciinema
```

With Yarn:

```console
yarn add slidev-addon-asciinema
```

With pnpm:

```console
pnpm add slidev-addon-asciinema
```

### Declare the addon

Either add in your `slides.md` top frontmatter:

```yaml
theme: ...
...
addons:
  - slidev-addon-asciinema
---
# Slides markdown
```

Or add it in your `package.json` file:

```json
{
  "scripts": {
    
  },
  "slidev": {
    "addons": [
      "slidev-addon-asciinema"
    ]
  }
}
```

### Use it in your presentation

```md
# Example

<Asciinema src="casts/yourcast.cast" />
```

The parameter `src` will look for static assets from the [`public` directory](https://sli.dev/custom/directory-structure.html#public). In this example, the file is be located at `your-project-root/public/casts/yourcast.cast`.

### Customize your player

All the[ `asciinema-player`'s options](https://github.com/asciinema/asciinema-player#options) are available via `:playerProps`. For example, one could change the speed and the number of lines of player's terminal with:

```md
# Example

<Asciinema src="casts/yourcast.cast" :playerProps="{speed: 2, rows: 23}"/>
```

### Base paths

If you are building your slides for [static hosting](https://sli.dev/guide/hosting.html#static-hosting) and you are using a different [base path](https://sli.dev/guide/hosting.html#base-path) (i.e.: you're using GitHub Pages). The component should work as expected, but remember to include the base path in your `vite.config.js` file.

```sh
slidev build --base /your-base-path
```

```js
export default {
  base: '/your-base-path',
};

```


## Fonts

You can specify the `asciinemaplayer` fonts by specifying the `terminalFontFamily` [player prop](https://github.com/asciinema/asciinema-player#fonts). Currently, only the following non-default fonts are supported:

- MesloLGS NF

If you want to use a different font, please open an issue or a PR ([see example](https://github.com/murilo-cunha/slidev-addon-asciinema/blob/main/components/asciinema-player.css#L2705-L2709)).

## Known issues

There are a couple of issues already identified

- Player placeholder is resized after playing cast - [#1](https://github.com/murilo-cunha/slidev-addon-asciinema/issues/1)
- Video's progress does not move in the same place where click happens - [#5](https://github.com/murilo-cunha/slidev-addon-asciinema/issues/5)

Would you like to contribute? Leave a PR! 🚀
