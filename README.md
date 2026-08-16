# 2048

A small terminal **2048** for [Omarchy](https://omarchy.org/). The board follows the theme you already have selected and fills the whole screen. Pick a board size, then join the tiles to reach 2048.

The game opens as a normal tiled window, so it joins whatever layout you are already using. Move and resize it with your usual keys.

## Install

```sh
omarchy plugin add https://github.com/your-user/omarchy-my-2048.git --enable
```

That clones the repo into `~/.config/omarchy/plugins/terminal.2048/`. Click the bar icon to open the panel, then Play. Or run the game directly:

```sh
~/.config/omarchy/plugins/terminal.2048/omarchy-2048
```

## Usage

Left click the bar icon for the panel. Right click starts a game. Escape closes the panel. `omarchy-shell shell summon terminal.2048` opens it the same way.

| Step | Action |
|---|---|
| **Pick size** | Choose 4×4 up to 8×8 in the menu |
| **Play** | Join equal tiles, reach 2048 |

| Key | Action |
|---|---|
| ← → ↑ ↓ / WASD | Move tiles |
| r | Retry |
| p | Pause |
| q / Esc | Menu, or quit from the menu |

The board renders to fill the entire terminal, with each tile sized to the chosen grid so a 4×4 board shows huge tiles and an 8×8 board shows smaller ones. Tiles are colored by value and follow your theme. Best score is tracked per board size in `~/.local/share/omarchy-2048/scores.json`. Last size and "keep going" live in `~/.local/state/omarchy/2048.json`.

## Configure

```sh
omarchy bar move terminal.2048 --section left
```

## Why this is safe

`omarchy plugin add` only clones the git repo. It does not run install scripts or request elevated privileges.

The game is Python 3 and the standard library. It does not open the network. It reads the current theme colors and writes scores and settings under your home directory. The bar widget launches that script in a terminal. Plugins stay off until you enable them.

## Remove

```sh
omarchy plugin remove terminal.2048
```
