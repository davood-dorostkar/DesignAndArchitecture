# Setup Java Environment in Linux

## Install Android Studio
- download the latest version of [Android Studio](https://developer.android.com/studio) for Linux. ([reference](https://developer.android.com/studio/install))

- install these libraries:
```sh
sudo apt update && sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386
```
- extract the file in `/usr/local/` for your user profile or `/opt/` for shared users.

```sh
tar xzf <Archive> -C /usr/local/
```
- add the installation directory to path (check if the below address is correct):
```sh
echo 'export PATH=/usr/local/android-studio/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

## install android SDK:
```sh
sudo apt update && sudo apt install android-sdk
```
change the ownership and permission if needed. the sdk by default is installed in `/usr/lib/android-sdk`. so:
```sh
sudo chown -R root:<USER> /usr/lib/android-sdk
sudo chmod -R 775 /usr/lib/android-sdk
```

## check if your PC supports KVM. 
- first install required packages:
```sh
sudo apt-get install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils cpu-checker
```
- this must report 1 or greater:
```sh
egrep -c '(vmx|svm)' /proc/cpuinfo
```
- run this. it tells you if you can use KVM:
```sh
sudo kvm-ok
```

## Download Android Emulator
### Automatic
you can download the emulator automatically when Android Studio runs for the first time. If you choose this way skip this part.

### Manual
- download a version in this [page](https://developer.android.com/studio/emulator_archive). This version is tested and stable: [33.1](https://redirector.gvt1.com/edgedl/android/repository/emulator-linux_x64-11237101.zip)

- the installation instructions are explained in the page. 
- extract the file into `$HOME/Android/Sdk`

## Setup Android Studio 
- run the Android Studio (you can run this everywhere, because we added to path):
```sh
studio.sh
```
- open a an existing project or make a new one. To open a project, find the file `build.gradle` and double click it.

- For the first time, it requires the sdk. give it the address of your sdk above.

- To enable Emulator ([reference](https://developer.android.com/studio/run/managing-avds)): 
  - go to `view > Tool Windows > Device Manager`. 
  - Then add a new virtual device. Select a device (like Pixel 4 XL) and an Android API (like 29). 
  - Then it will download required files and install it.

## Get Project Dependencies
You may need dependencies like `maven` or `gradle`. as it is very project-specific, let it be installed automatically. run or build the project and it will automatically detect and install required packages.