# Delφ Theme

Indigo blue dark and light color themes for VS Code. The dark theme uses the delφ brand blue `#062a55` as the editor background, and the light theme uses `#f8fafc`. The same palette is used by the delφ terminal UI.

| Delφ Dark | Delφ Light |
|---|---|
| ![Delφ Dark](images/dark.png) | ![Delφ Light](images/light.png) |

## Install

Install it from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ludikrizz.delphi-theme):

1. Open the Extensions view (`Ctrl+Shift+X`).
2. Search for **Delφ Theme**.
3. Select **Install**.

To install it from the source instead:

1. Clone this repo.
2. Run `npm run package`. This makes `delphi-theme-0.1.0.vsix`.
3. Run `code --install-extension delphi-theme-0.1.0.vsix`.

## Activate

1. Open the Command Palette (`Ctrl+Shift+P`).
2. Select **Preferences: Color Theme**.
3. Select **Delφ Dark** or **Delφ Light**.

To switch with the OS light or dark mode, add this to your `settings.json`:

```json
"window.autoDetectColorScheme": true,
"workbench.preferredDarkColorTheme": "Delφ Dark",
"workbench.preferredLightColorTheme": "Delφ Light"
```

## Zed

`zed/delphi.json` has both themes for the Zed editor.

1. Copy `zed/delphi.json` to `%APPDATA%\Zed\themes\` (Windows) or `~/.config/zed/themes/` (macOS and Linux).
2. In Zed, open the theme selector (`Ctrl+K Ctrl+T`).
3. Select **Delφ Dark** or **Delφ Light**.

## Herdr

`herdr/delphi.toml` sets the colors of the [Herdr](https://herdr.dev/) UI. Herdr uses the dark colors, and the light colors when the host terminal reports a light appearance.

1. Add the contents of `herdr/delphi.toml` to the end of your Herdr `config.toml` (`%APPDATA%\herdr\` on Windows, `~/.config/herdr/` on macOS and Linux).
2. In Herdr, open the global menu and select **reload config**.

Herdr accepts only its built-in theme names, so the file sets no theme name.

## Palette

The main syntax colors of Delφ Dark:

| Role | Color |
|---|---|
| Background | `#062a55` |
| Text | `#eef1f6` |
| Accent | `#7ec2fa` |
| Keyword | `#d396fe` |
| Declaration (`const`, `class`) | `#92ddff` |
| Function | `#12c5fe` |
| String | `#6be36c` |
| Number | `#fbd604` |
| Type | `#08dbd4` |
| Parameter | `#ff9e64` |
| Property, error | `#ff5071` |
| Constant, tag | `#ff89b0` |
| Comment | `#9fa5ae` |

`palette.json` has all the colors of both themes.

## Change the colors

To change a color in the themes:

1. Edit `palette.json`. It has a `dark` and a `light` object with the same keys.
2. Run `npm run build`. This writes `themes/delphi-dark.json`, `themes/delphi-light.json`, `zed/delphi.json` and `herdr/delphi.toml`.
3. Package and install again (see [Install](#install)).

To change one color only on your machine, use the settings that VS Code has for this:

```json
"workbench.colorCustomizations": {
	"[Delφ Dark]": { "editor.lineHighlightBackground": "#15395f" }
},
"editor.tokenColorCustomizations": {
	"[Delφ Dark]": { "comments": "#8a99aa" }
}
```

## Files

| Path | Contents |
|---|---|
| `palette.json` | The source colors, exported from the delφ palette page |
| `build.mjs` | Maps the palette to VS Code window colors, TextMate scopes and semantic tokens, and to the Zed and Herdr themes |
| `themes/` | The built VS Code theme files (commit them after each build) |
| `zed/` | The built Zed theme file (commit it after each build) |
| `herdr/` | The built Herdr theme file (commit it after each build) |
| `images/` | README screenshots of VS Code |

## License

[MIT](LICENSE)
