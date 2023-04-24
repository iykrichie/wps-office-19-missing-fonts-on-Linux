# Installation of missng WPS-Office fonts to fix the error below
Solution to the error - Some formula symbols might not be displayed correctly due to missing fonts symbol.


The following commands will move the missing fonts from
downloaded/cloned folder to your system wps office fonts folder.

This should work for all linux distros.

1a) Clone this repo somewhere and open the folder 
1b) Download and extract the .zip GitHub automatically makes. Then open that folder. 

2) Move or Copy the folder '`special-wps-office-fonts`' to `/usr/share/fonts/` 

3) Update your font-cache by entering these commands
based on your distrobution: 

Mint/Ubuntu/Debian/etc
`sudo mv -f *.* /usr/share/fonts/ ; sudo fc-cache -f -v ; cd`

Arch/Manjaro/Antergos/etc 
`sudo mv -f *.* /usr/share/fonts/ ; sudo fc-cache -f -v ; cd`

Fedora/OpenMandriva/Mageia/etc
`sudo mv -f *.* /usr/share/fonts/ ; sudo fc-cache -f -v ; cd`

Other Distros
`sudo mv -f *.* /usr/share/fonts/ ; sudo fc-cache -f -v ; cd`

### 

You're done! WPS Office should now load properly! Awesome!

