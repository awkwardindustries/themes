# Awkward Industries Themes

A Cursor / VS Code theme pack. Install once, then pick any contributed theme from **Preferences: Color Theme**.

## Themes

| Theme | Notes |
| --- | --- |
| [Macrodata Refinement](#macrodata-refinement) | CRT navy and the four bin colors from the *Severance* terminal |
| [Matrix](#matrix) | Ustym Ukhman's Matrix theme, bundled so it does not need a second install |

To add another theme later: put the JSON in `themes/`, register it in `contributes.themes`, and add a `build:<name>` script if it is generated.

## Install

1. Clone this repo.
2. Command Palette → **Developer: Install Extension from Location...**
3. Select this folder.
4. Command Palette → **Preferences: Color Theme** and choose a theme from the pack.

Or from a terminal in this folder:

```bash
npm run build
npx @vscode/vsce package --no-dependencies
cursor --install-extension awkward-industries-themes-0.1.1.vsix
```

(`code --install-extension` works the same in VS Code.)

Open this folder and press `F5` to preview the pack in an Extension Development Host.

Remove leftover `workbench.colorCustomizations` and `editor.tokenColorCustomizations` from user settings after switching. Those overrides will fight the pack.

## Macrodata Refinement

A dark theme modeled on the Macrodata Refinement terminal: cyan hairlines on CRT navy, with Woe, Frolic, Dread, and Malice used for syntax and terminal ANSI colors.

Syntax colors start from [SkaldAlfar's screenshot-sampled settings](https://github.com/SkaldAlfar/MacrodataRefinementComputerTheme). The theme file replaces leftover VS Code defaults that leaked into the agent panel (gray input/chat cards) and the terminal (stock green/yellow ANSI).

| Role | Hex | Use |
| --- | --- | --- |
| Background | `#081e28` | Editor, sidebar, panel, agent chrome |
| Raised | `#0c2834` | Inputs, chat bubbles, cards |
| Border | `#587f88` | Hairlines and widgets |
| Cyan / WO | `#79e6ff` | UI text, functions |
| Ice | `#d7f0ff` | Strings, numbers, caret |
| Mint / MA | `#12f2b3` | Keywords, inserts, ANSI green |
| Cream / FC | `#eedc44` | Types, modified files, ANSI yellow |
| Pink / DR | `#ffaaf2` | Variables, deletes, ANSI magenta |
| Blue | `#2f94ff` | Operators |
| Comment | `#3d6a78` | Dim teal instead of One Dark gray |

```bash
npm run build:macrodata-refinement
```

That regenerates `themes/macrodata-refinement-color-theme.json` from `sources/macrodata-refinement/skaldalfar-user-settings.txt` plus the workbench colors in `scripts/build-macrodata-refinement.mjs`.

Cursor's detached Agents Window still ignores some theme tokens. The in-editor agent panel should pick up the teal surfaces via `chat.*`, `agents*`, and `input.*` keys.

Credit: [SkaldAlfar/MacrodataRefinementComputerTheme](https://github.com/SkaldAlfar/MacrodataRefinementComputerTheme); look from Lumon Industries Macrodata Refinement, *Severance*.

## Matrix

[Ustym Ukhman's Matrix Theme](https://marketplace.visualstudio.com/items?itemName=UstymUkhman.matrix-theme), included as-is under MIT. After installing this pack, choose **Matrix** from **Preferences: Color Theme**. You can uninstall the marketplace extension if you only want one copy.

Source and license: [UstymUkhman/matrix-theme](https://github.com/UstymUkhman/matrix-theme), `third_party/matrix-theme/`.
