To initialize a shallow clone

    repo init --depth=1 -u https://github.com/Seplx/orangefox-7.1-manifest.git

Then to sync up:

    repo sync -j8 --force-sync

Then to build:

     cd <source-dir>
     
     . build/envsetup.sh && lunch omni_<device>-eng && mka recoveryimage
     
