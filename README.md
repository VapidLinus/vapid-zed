# vapid-zed

My [Zed](https://zed.dev) config: Vim mode on the JetBrains keymap, with leader bindings taken mostly from [Intellimacs](https://github.com/MarcoIeni/intellimacs) and tuned for a Swedish layout (`sv-qwerty`) and my custom Dygma Defy layout.

## Setup

Install [Zed](https://zed.dev/download). It reads its config from `%APPDATA%\Zed`, so clone this repo into that folder while it is empty or missing:

```powershell
git clone https://github.com/VapidLinus/vapid-zed.git $env:APPDATA\Zed
```

Install the [Inter](https://rsms.me/inter/) and [JetBrains Mono](https://www.jetbrains.com/lp/mono/) fonts on Windows. `settings.json` uses Inter for the UI and JetBrains Mono for the editor and terminal. Then install the `jetbrains-themes` and `jetbrains-new-ui-icons` extensions in Zed for the theme and icons. The keymap relies on `"vim_mode": true` and `"base_keymap": "JetBrains"`, which `settings.json` sets.

`which_key` is on, so pausing for 300 ms in the middle of a sequence lists the keys that can follow.

## Reading the tables

Everything below differs from Zed's JetBrains keymap and Vim mode. Anything not listed works as Zed ships it. A capital letter means Shift, so <kbd>F</kbd> is <kbd>Shift</kbd>+<kbd>f</kbd>. Leader bindings work in normal and visual mode unless the row says normal only.

## Changed Vim keys

| Keys | Mode | Does | Zed default |
|---|---|---|---|
| <kbd>Space</kbd> | normal, visual | Leader, waits for the rest of the sequence | Move right |
| <kbd>'</kbd> | normal, visual | Jump to a mark's exact position | Jump to the mark's line |
| <kbd>`</kbd> | normal, visual | Jump to a mark's line | Jump to the exact position |
| <kbd>g</kbd> <kbd>L</kbd> | normal, visual | End of line | Select previous match |
| <kbd>g</kbd> <kbd>H</kbd> | normal, visual | First non-blank character | Unbound |
| <kbd>m</kbd> <kbd>m</kbd> | normal | Toggle bookmark | Set mark `m` |
| <kbd>z</kbd> <kbd>m</kbd> | normal | Fold all, same as <kbd>z</kbd> <kbd>M</kbd> | Unbound |
| <kbd>z</kbd> <kbd>r</kbd> | normal | Unfold all, same as <kbd>z</kbd> <kbd>R</kbd> | Unbound |

## Swedish keys

<kbd>ö</kbd> is where US keyboards have <kbd>;</kbd>, and <kbd>å</kbd> is where they have <kbd>[</kbd>.

| Keys | Mode | Does |
|---|---|---|
| <kbd>ö</kbd> | insert, visual | Back to normal mode, like <kbd>Esc</kbd>. In insert mode this means <kbd>ö</kbd> can't be typed |
| <kbd>Ö</kbd> | normal, visual | Command line, same as <kbd>:</kbd> |
| <kbd>Ö</kbd> | insert | Leave insert mode and open the command line |
| <kbd>å</kbd> | normal, visual | Same group as <kbd>Space</kbd> <kbd>m</kbd>, so <kbd>å</kbd> <kbd>r</kbd> <kbd>r</kbd> renames |

## Leader

| Space then | Does |
|---|---|
| <kbd>Space</kbd> | Command palette |
| <kbd>'</kbd> | Terminal |
| <kbd>*</kbd> | Find references |
| <kbd>/</kbd> | Search the project |
| <kbd>?</kbd> | Keymap editor |
| <kbd>Tab</kbd> | Previous file |
| <kbd>1</kbd> … <kbd>9</kbd> <kbd>0</kbd> | Go to tab 1 to 10 |
| <kbd>Y</kbd> / <kbd>P</kbd> | Yank / paste with the system clipboard |

### <kbd>Space</kbd> <kbd>b</kbd> tabs

| Then | Does |
|---|---|
| <kbd>b</kbd> | Tab switcher |
| <kbd>n</kbd> <kbd>k</kbd> | Next tab |
| <kbd>p</kbd> <kbd>j</kbd> | Previous tab |
| <kbd>0</kbd> / <kbd>$</kbd> | First / last tab |
| <kbd>d</kbd> | Close tab |
| <kbd>Ctrl</kbd>+<kbd>d</kbd> | Close other tabs |
| <kbd>x</kbd> | Close all tabs |
| <kbd>u</kbd> | Reopen closed tab |
| <kbd>t</kbd> | Pin or unpin tab |
| <kbd>s</kbd> | New file |
| <kbd>P</kbd> | Replace the whole file with the clipboard. Normal only |

### <kbd>Space</kbd> <kbd>B</kbd> bookmarks

| Then | Does |
|---|---|
| <kbd>t</kbd> | Toggle bookmark |
| <kbd>T</kbd> | Toggle bookmark with a label |
| <kbd>n</kbd> | Next bookmark |
| <kbd>p</kbd> <kbd>N</kbd> | Previous bookmark |
| <kbd>l</kbd> | List bookmarks |

### <kbd>Space</kbd> <kbd>c</kbd> comments

| Then | Does |
|---|---|
| <kbd>l</kbd> | Toggle line comment. <kbd>Space</kbd> <kbd>;</kbd> <kbd>;</kbd> does the same |
| <kbd>b</kbd> | Toggle block comment |
| <kbd>p</kbd> | Comment the paragraph. Normal only |
| <kbd>y</kbd> | Copy the line and comment out the copy above it. Normal only |
| <kbd>t</kbd> | Comment from the top of the file to the cursor. Normal only |

### <kbd>Space</kbd> <kbd>e</kbd> errors

| Then | Does |
|---|---|
| <kbd>n</kbd> | Next diagnostic |
| <kbd>p</kbd> <kbd>N</kbd> | Previous diagnostic |
| <kbd>l</kbd> | Diagnostics panel |
| <kbd>r</kbd> | Code actions |
| <kbd>x</kbd> | Hover info for the error under the cursor |

### <kbd>Space</kbd> <kbd>f</kbd> files

| Then | Does |
|---|---|
| <kbd>f</kbd> <kbd>F</kbd> <kbd>r</kbd> | Find file |
| <kbd>s</kbd> / <kbd>S</kbd> | Save / save all |
| <kbd>t</kbd> | Project panel |
| <kbd>n</kbd> | New file |
| <kbd>b</kbd> | List bookmarks |
| <kbd>y</kbd> <kbd>y</kbd> | Copy the file's path |
| <kbd>e</kbd> <kbd>d</kbd> | Open `settings.json` |
| <kbd>e</kbd> <kbd>r</kbd> | Open `keymap.json` |

### <kbd>Space</kbd> <kbd>g</kbd> git

| Then | Does |
|---|---|
| <kbd>s</kbd> <kbd>G</kbd> | Git panel |
| <kbd>b</kbd> | Switch branch |
| <kbd>p</kbd> | Push |
| <kbd>v</kbd> <kbd>+</kbd> | Pull |
| <kbd>v</kbd> <kbd>g</kbd> | Blame |
| <kbd>f</kbd> <kbd>l</kbd> | File history |
| <kbd>c</kbd> / <kbd>i</kbd> | Clone / init |
| <kbd>d</kbd> | Go to definition |

### <kbd>Space</kbd> <kbd>j</kbd> jump

| Then | Does |
|---|---|
| <kbd>j</kbd> | Jump to a word by its label |
| <kbd>e</kbd> | Outline of the file |
| <kbd>c</kbd> <kbd>s</kbd> | Project symbols |
| <kbd>d</kbd> <kbd>D</kbd> | Project panel |
| <kbd>=</kbd> | Format |
| <kbd>n</kbd> | Split the line at the cursor. Normal only |
| <kbd>o</kbd> | Split the line at the cursor and stay at the end of the first half. Normal only |

### <kbd>Space</kbd> <kbd>m</kbd> or <kbd>å</kbd> code

| Then | Does |
|---|---|
| <kbd>g</kbd> <kbd>g</kbd> | Go to definition |
| <kbd>g</kbd> <kbd>i</kbd> | Go to implementation |
| <kbd>g</kbd> <kbd>t</kbd> | Go to type definition |
| <kbd>h</kbd> <kbd>h</kbd> | Hover info |
| <kbd>h</kbd> <kbd>u</kbd> / <kbd>h</kbd> <kbd>U</kbd> | Find references |
| <kbd>h</kbd> <kbd>c</kbd> | Incoming calls |
| <kbd>r</kbd> <kbd>r</kbd> | Rename |
| <kbd>r</kbd> <kbd>g</kbd> / <kbd>r</kbd> <kbd>R</kbd> | Code actions |
| <kbd>r</kbd> <kbd>i</kbd> | Organize imports |
| <kbd>r</kbd> <kbd>n</kbd> | New file |
| <kbd>=</kbd> <kbd>=</kbd> | Format |
| <kbd>p</kbd> <kbd>r</kbd> | Run a task |
| <kbd>d</kbd> <kbd>b</kbd> | Toggle breakpoint |
| <kbd>d</kbd> <kbd>B</kbd> | Debug panel |
| <kbd>d</kbd> <kbd>d</kbd> | Start debugging |
| <kbd>d</kbd> <kbd>c</kbd> | Continue |
| <kbd>d</kbd> <kbd>n</kbd> / <kbd>d</kbd> <kbd>s</kbd> / <kbd>d</kbd> <kbd>o</kbd> | Step over / into / out |

### <kbd>Space</kbd> <kbd>p</kbd> project

| Then | Does |
|---|---|
| <kbd>f</kbd> <kbd>b</kbd> <kbd>h</kbd> <kbd>r</kbd> | Find file |
| <kbd>p</kbd> | Recent projects |
| <kbd>t</kbd> <kbd>D</kbd> | Project panel |
| <kbd>v</kbd> | Git panel |
| <kbd>!</kbd> | Terminal |
| <kbd>R</kbd> | Search and replace in the project |
| <kbd>T</kbd> | Rerun the last task |

### <kbd>Space</kbd> <kbd>s</kbd> search

| Then | Does |
|---|---|
| <kbd>f</kbd> | Find in file |
| <kbd>r</kbd> | Replace in file |
| <kbd>s</kbd> <kbd>p</kbd> <kbd>l</kbd> | Search the project. <kbd>Space</kbd> <kbd>r</kbd> <kbd>s</kbd> does the same |
| <kbd>P</kbd> | Find references |
| <kbd>e</kbd> | Rename |
| <kbd>E</kbd> | Find file |

### <kbd>Space</kbd> <kbd>t</kbd> and <kbd>T</kbd> toggles

| Then | Does |
|---|---|
| <kbd>t</kbd> <kbd>l</kbd> | Soft wrap |
| <kbd>t</kbd> <kbd>n</kbd> | Line numbers |
| <kbd>t</kbd> <kbd>r</kbd> | Relative line numbers |
| <kbd>t</kbd> <kbd>i</kbd> | Indent guides |
| <kbd>T</kbd> <kbd>t</kbd> | Centered layout |
| <kbd>T</kbd> <kbd>m</kbd> | Hide or show all docks |
| <kbd>T</kbd> <kbd>p</kbd> | Full screen |

### <kbd>Space</kbd> <kbd>w</kbd> windows

| Then | Does |
|---|---|
| <kbd>v</kbd> / <kbd>s</kbd> | Move the tab into a new split to the right / below |
| <kbd>/</kbd> <kbd>V</kbd> | Split right |
| <kbd>-</kbd> <kbd>S</kbd> | Split down |
| <kbd>h</kbd> <kbd>j</kbd> <kbd>k</kbd> <kbd>l</kbd> | Focus the pane in that direction. Arrow keys work too |
| <kbd>w</kbd> | Next pane |
| <kbd>m</kbd> | Zoom the pane |
| <kbd>d</kbd> <kbd>x</kbd> | Close all tabs and panes |

### <kbd>Space</kbd> <kbd>x</kbd> text

| Then | Does |
|---|---|
| <kbd>J</kbd> / <kbd>K</kbd> | Move the line down / up |
| <kbd>u</kbd> / <kbd>U</kbd> | Lowercase / uppercase the character. Normal only |
| <kbd>t</kbd> <kbd>c</kbd> | Swap the character with the one before it. Normal only |
| <kbd>t</kbd> <kbd>l</kbd> | Swap the line with the one above it. Normal only |

### <kbd>Space</kbd> <kbd>q</kbd> quit

| Then | Does |
|---|---|
| <kbd>q</kbd> <kbd>f</kbd> | Close the window |
| <kbd>s</kbd> | Save all and close the window. Normal only |
| <kbd>Q</kbd> | Quit Zed |

### Smaller groups

| Space then | Does |
|---|---|
| <kbd>i</kbd> <kbd>j</kbd> / <kbd>i</kbd> <kbd>k</kbd> | Empty line below / above. Normal only |
| <kbd>n</kbd> <kbd>+</kbd> / <kbd>n</kbd> <kbd>=</kbd> / <kbd>n</kbd> <kbd>-</kbd> | Increment, increment, decrement the number |
| <kbd>z</kbd> <kbd>+</kbd> / <kbd>z</kbd> <kbd>=</kbd> / <kbd>z</kbd> <kbd>-</kbd> / <kbd>z</kbd> <kbd>0</kbd> | Bigger, bigger, smaller, reset editor font. <kbd>z</kbd> <kbd>x</kbd> plus the same key does the same |
| <kbd>R</kbd> <kbd>r</kbd> <kbd>a</kbd> <kbd>s</kbd> | Run a task |
| <kbd>v</kbd> <kbd>i</kbd> <kbd>f</kbd> | Reveal the file in the project panel |
| <kbd>v</kbd> <kbd>i</kbd> <kbd>e</kbd> | Reveal the file in Explorer |
| <kbd>h</kbd> <kbd>k</kbd> / <kbd>h</kbd> <kbd>d</kbd> <kbd>k</kbd> / <kbd>h</kbd> <kbd>d</kbd> <kbd>b</kbd> | Keymap editor |

## With no file open

An empty pane still takes these: <kbd>Space</kbd> then <kbd>Space</kbd>, <kbd>'</kbd>, <kbd>f</kbd> <kbd>f</kbd>, <kbd>f</kbd> <kbd>r</kbd>, <kbd>f</kbd> <kbd>t</kbd>, <kbd>p</kbd> <kbd>f</kbd>, <kbd>p</kbd> <kbd>p</kbd>, <kbd>f</kbd> <kbd>e</kbd> <kbd>d</kbd> and <kbd>f</kbd> <kbd>e</kbd> <kbd>r</kbd>, with the same meaning as above.
