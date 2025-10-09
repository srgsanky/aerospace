# srgsanky's Aerospace configuration

<https://nikitabobko.github.io/AeroSpace/guide.html>

## Installation

```bash
brew install --cask nikitabobko/tap/aerospace
```

## Clone the configuration

```bash
mkdir -p ~/.config/
git clone https://github.com/srgsanky/aerospace ~/.config/aerospace
```


| What?                                           | Keybinding                             |
| ----------------------------------------------- | -------------------------------------- |
| Focus **workspace**                             | `alt-1`                                |
| Focus windows                                   | `alt-h/j/k/l`                          |
| Move current window within **workspace**        | `alt-shift-h/j/k/l`.                   |
| Move currently focused window to **workspace**  | `alt-shift-1`                          |
| Switch focus between most recent two workspaces | `alt-tab`                              |
| Switch between tiles and accoridion             | `alt-/` (tiles), `alt-,` (accordion)   |
| Move **workspace** to monitor                   | `alt-shift-tab`                        |
| Resize                                          | `alt-shift-minus` or `alt-shift-+`     |
| Stop managing window/start managing window      | `alt-shift-o` (out)/`alt-shift-i` (in) |
| Full screen in desktop                          | `alt-shift-f`                          |
| MacOS full screen                               | `alt-shift-t`                          |
| MacOS minimize                                  | `alt-shift-m`                          |
| Enter service mode                              | `alt-shift-;` (exit by using `esc`)    |


## How to add rules for a new app?

List the apps

```bash
aerospace list-apps
# ai.perplexity.comet
```

Add commands to `aerospace.toml`

```toml
[[on-window-detected]]
if.app-id = 'ai.perplexity.comet'
run = ['layout floating', 'move-node-to-workspace 2']
```

Few rules

1. `move-node-to-workspace` has to be the last in a multi-instruction run configuration
1. Only `layout floating`/`layout tiling` are support
1. `check-further-callbacks` is like break statement in switch. No further rule is evaluated if false (the default).

