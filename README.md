## AOSP Script PreInstall ##

**Script Bourne Shell** for install apps in the Android system after wipe data.

This tool is usefull for put preloading apps and this apps persist after hard reset.

### How use ###

You need add one native service to the 'init' resources call 'preinstall' for the init process.

The syntax for these .rc files is documented in a readme file in the source tree. See the Android init language reference.

See also [http://www.androidenea.com/2009/08/init-process-and-initrc.html ](http://www.androidenea.com/2009/08/init-process-and-initrc.html )

See also [http://droidcore.blogspot.com/2012/12/how-to-edit-initrc-in-android.html](http://droidcore.blogspot.com/2012/12/how-to-edit-initrc-in-android.html)

The service run in the user space the script in the `/system/bin` folder on the device, this file is called `preinstall.sh`, these commands check always on init if exist the file `/data/system/notfirstrun` else this file is created for not run the complete script again.

All apps need put in the `/system/preinstall` folder and the script call the Package Manager in Android to install this apps.
