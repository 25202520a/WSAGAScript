# IT'S **WIP**

# This readme is being updated multiple times. I'm aware that's not clear, I'm going to resolve it ASAP.

# As a temporary measure I made a tutorial
[![How to install Google Apps (Play Store) on WSA (Windows Subsystem Android)](http://img.youtube.com/vi/rIt00xDp0tM/0.jpg)](http://www.youtube.com/watch?v=rIt00xDp0tM "How to install Google Apps (Play Store) on WSA (Windows Subsystem Android)")

## SIGN IN DOESN'T WORK CURRENTLY. 
### THIS IS FOR TESTING

Download MSIXBUNDLE (use store rg-adguard to download the msixbundle, Package id: 9P3395VX91NR, Ring: SLOW, size is around 1.2GB)

INSTALL WSL2 (ubuntu/debian, any other distro could work)

INSTALL unzip lzip 

DOWNLOAD GAPPS PICO FROM OPENGAPPS (x86_64, 11, PICO)

EXTRACT MSIXBUNDLE, EXTRACT MSIX (YOUR ARCH) TO A FOLDER, DELETE (APPXMETADATA, APPXBLOCKMAP, APPXSIGNATURE, \[CONTENT_TYPES\])

COPY IMAGES (SYSTEM.IMG, SYSTEM_EXT.IMG, PRODUCT.IMG, VENDOR.IMG) TO #IMAGES

COPY (GAPPS PICO ZIP) TO #GAPPS

EDIT (VARIABLES.sh) AND SET ROOT FOLDER

EXECUTE AS SUDO:
- extract_gapps_pico.sh
- extend_and_mount_images.sh
- apply.sh
- unmount_images.sh

COPY IMAGES FROM (#IMAGES FOLDER) TO YOUR EXTRACTED MSIX FOLDER

OPEN POWERSHELL (NOT CORE) AS ADMIN, EXECUTE (Add-AppxPackage -Register PATH_TO_EXTRACTED_MSIX\AppxManifest.xml)
DEVELOPMENT MODE HAS TO BE ENABLED BEFOREHAND. MAKE SURE YOU DON'T HAVE WSA ALREADY INSTALLED, THEY CAN'T COEXIST.

RUN WSA WITH GAPPS, ENJOY

# WORKAROUND FOR SIGN IN ISSUE:
## (ADB SHELL ROOT WITH su)

COPY (kernel FILE) FROM (misc FOLDER) TO (Tools FOLDER) IN YOUR EXTRACTED MSIX FOLDER

NOW YOU CAN USE su IN ADB SHELL
ENTER ADB SHELL, TYPE su THEN TYPE setenforce 0
YOU CAN NOW SIGN IN


This readme will be rewritten very soon
