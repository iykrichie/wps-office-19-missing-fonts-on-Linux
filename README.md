
# Fix for missing wps-office-19 fonts

Solution to the error - Some formula symbols might not be displayed correctly due to missing fonts symbol.

The following solution is a command will copy the missing fonts from the downloaded/cloned folder to your system WPS Office fonts folder. This should work for all Linux distros.

1. Clone this repo somewhere and open the folder.
2. Download and extract the .zip GitHub automatically makes. Then open that folder.
3. Move or copy the folder `special-wps-office-fonts` to `/usr/share/fonts/`.
4. Update your font-cache by entering these commands below based on your distribution.

* Mint/Ubuntu/Debian/etc
    
        ``` sudo cp -f *.* /usr/share/fonts/ && sudo fc-cache -f -v

* This should work (but have not been tested) on other distros.
    

You're done! WPS Office should now load properly! Awesome!

### Notes

* The commands above are for the Linux operating system. For other operating systems, please refer to the WPS Office documentation.
* If you are still having problems after following these steps, please contact WPS Office support for assistance.
