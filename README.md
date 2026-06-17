# WPS Office — Missing Fonts on Linux

## The problem

Some formula symbols and special characters might not display correctly in WPS Office on Linux. This happens because WPS expects certain Windows-style fonts (Symbol, Wingdings, etc.) that aren't installed by default on Linux systems.

## The fix

This repo contains the missing font files. Copying them into your system fonts folder and refreshing the font cache resolves the display issue. This should work on all major Linux distributions.

### Step 1 — Get the fonts

Either clone the repo:

```bash
git clone https://github.com/iykrichie/wps-office-19-missing-fonts-on-Linux.git
cd wps-office-19-missing-fonts-on-Linux
```

Or download the ZIP from GitHub (Code → Download ZIP), extract it, and open the extracted folder in a terminal.

### Step 2 — Go into the fonts folder

The actual font files live inside the `special-wps-office-fonts` subfolder. Make sure you `cd` into **that** folder — not the repo root — before running the next command:

```bash
cd special-wps-office-fonts
ls
```

You should see files like `mtextra.ttf`, `symbol.ttf`, `WEBDINGS.TTF`, `wingding.ttf`, `WINGDNG2.ttf`, `WINGDNG3.ttf`. If you don't see these, you're probably one directory level off — run `find . -iname "*.ttf"` from the repo root to locate them.

### Step 3 — Copy the fonts and refresh the cache

From inside `special-wps-office-fonts`, run:

```bash
sudo cp -f *.ttf *.TTF /usr/share/fonts/
sudo fc-cache -f -v
```

This copies only the font files (not the whole folder or the README) into your system fonts directory, then rebuilds the font cache so the system recognizes them.

### Step 4 — Restart WPS Office

Close and reopen WPS Office. Formula symbols and special characters should now render correctly.

## Notes

- These instructions are for Linux. For other operating systems, refer to the [WPS Office documentation](https://www.wps.com/).
- If you accidentally copy the *entire* repo folder into `/usr/share/fonts/` instead of just the font files, it will still work, but it's tidier to have only the `.ttf` files there. You can clean this up by moving the fonts up a level and removing the leftover folder/README.
- If you're still having display issues after following these steps, please open an issue on this repo or contact WPS Office support.
