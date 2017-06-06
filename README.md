android-openssl
===============

Android NDK openssl build script for original repository(https://www.openssl.org/)

modified version of setenv-android.sh and build script support all architectures in the android NDK

You can find the prebuilt binaries on the [prebuild branch](https://github.com/paulo-raca/android-openssl/tree/prebuilt).

see details : http://wiki.openssl.org/index.php/Android

Here are the instructions for 1.1.0f: 

1. unpack the tar.gz 
2. get setenv script github.com/alexcohn/…
3. create directory prebuilt/armeabi, chdir to this directory
4. prepare environment: 

ANDROID_NDK_ROOT=~/Library/Android/sdk/ndk-bundle ANDROID_ARCH=arm ANDROID_API="android-14" . <path-to>/setenv-android-mod.sh 

5. run command <path-to-OpenSSL>/Configure shared android -I$ANDROID_DEV/include
6. edit Makefile - remove all `.$(SHLIB_MAJOR).$(SHLIB_MINOR)` (and also `$(SHLIB_MAJOR).$(SHLIB_MINOR)` without `.` in front). 
7. run make 
8. repeat 1-7 for x86
