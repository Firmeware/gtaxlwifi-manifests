# Manifest for building LineageOS 20.0 for gtaxlwifi, gtaxllte, gtanotexlwifi, and gtanotexllte

`gtaxlwifi` is the codename for the WiFi-only variant of the Samsung Galaxy Tab A 10.1" (2016), with model SM-T580.

`gtaxllte` is the codename for the LTE variant of the Samsung Galaxy Tab A 10.1" (2016), with model SM-T585, and also with SM-T585N0 and SM-T585C for Korea and China respectively.

`gtanotexlwifi` is the codename for the WiFi-only variant of the Samsung Galaxy Tab A 10.1" (2016) **with S-Pen**, with model SM-P580, and also with SM-P583 for China.

`gtanotexllte` is the codename for the LTE variant of the Samsung Galaxy Tab A 10.1" (2016) **with S-Pen**, with models SM-P585, SM-P585M, SM-P585Y, SM-P585N0, and SM-P588C.

Some extremely basic instructions:
- Make a new directory for LineageOS sources and enter it:
```
mkdir lineage-20.0
cd lineage-20.0
```

- Initialize repo in this directory with the LineageOS 20.0 android repository:
```
repo init -u https://github.com/LineageOS/android.git -b lineage-20.0
```

- Clone this repository to .repo/local_manifests for roomservice.xml containing the repositories needed to build for these devices:
```
git clone https://github.com/Firmeware/gtaxlwifi-manifests.git -b lineage-20.0 .repo/local_manifests
```

- Sync all of the repositories in manifests (including LineageOS manifests):
```
repo sync --force-sync --no-tags --no-clone-bundle -c
```

- Finally, build as you like. For example, for a recovery-installable package for gtaxlwifi:
```
. build/envsetup.sh
lunch lineage_gtaxlwifi-userdebug
mka otapackage
```
