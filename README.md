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

### Step 2 — Copy the fonts and refresh the cache

Run:

```bash
sudo cp -f *.ttf *.TTF /usr/local/share/fonts/
```
for a system-wide installation,
#### OR
```bash
cp -f *.ttf *.TTF ~/.local/share/fonts
```
for a user-wide installation. Then, run:
```bash
sudo fc-cache -f -v
```

This copies only the font files (not the whole folder or the README) into your locally-managed system fonts directory or into a user fonts directory, then rebuilds the font cache so the system recognizes them.

### Step 3 — Restart WPS Office

Close and reopen WPS Office. Formula symbols and special characters should now render correctly.

## Notes

- These instructions are for Linux. For other operating systems, refer to the [WPS Office documentation](https://www.wps.com/).
- If you accidentally copy the _entire_ repo folder into your preferred installation directory, it will still work, but it's tidier to have only fonts there. You can clean this up by moving the fonts up a level and removing the leftover folder/README.
- If you're still having display issues after following these steps, please open an issue on this repo or contact WPS Office support.
