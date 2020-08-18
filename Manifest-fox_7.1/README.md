<p align="center">
  <img width="520" height="200" src="logo.jpg">
</p>

# [Download prebuilt](https://gitlab.com/OrangeFox/OrangeFox-download) | [OrangeFox Site](https://mryacha.github.io/OrangeFox-Site/)
---------------
## Automatically downloads only Xiaomi Redmi Note 4X(mido) files, if you want to build for other devices, you will need to copy files manually ##

### Build Script Variant: ###
---------------
In terminal:

You can use a build script

    wget https://gitlab.com/OrangeFox/Manifest/raw/master/Build.sh
    sudo bash Build.sh

## Prepare to build manually ##

update all packages

    sudo apt update && sudo apt upgrade -y
    
use a [script](https://github.com/akhilnarang/scripts) for download all requare require packages

    cd ~ && sudo apt install git axel -y && git clone https://github.com/akhilnarang/scripts && cd scripts && sudo bash setup/android_build_env.sh && sudo bash setup/install_android_sdk.bash

## Sync and Build manually ##
---------------

To get started with building OrangeFox Recovery, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

To initialize your local repository using the minimal-manifest-twrp omni trees to build OrangeFox, use a command like this:

    repo init -u https://gitlab.com/OrangeFox/Manifest.git -b fox_7.1
    
To initialize a shallow clone (recommend), which will save even more space, use a command like this:

    repo init --depth=1 -u https://gitlab.com/OrangeFox/Manifest.git -b fox_7.1

Then to sync up:

    repo sync -j8 --force-sync

Then to build:

     cd <source-dir>
     
     . build/envsetup.sh && lunch omni_<device>-eng && mka recoveryimage
     
