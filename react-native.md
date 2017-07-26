# React Native Note

initial react native app

```
$ npm install -g react-native
$ react-native init <APP_NAME>
```

## Setup for Android

Prerequisite

```
# install Java and android-sdk with brew cask
$ brew cask install java android-sdk

# export ANDROID_HOME, it will be /usr/local/share/android-sdk if install with brew cask
$ echo "export ANDROID_HOME=/usr/local/share/android-sdk" >> ~/.zshrc # OR ~/.bashrc
```

AVD

```
# Mac
CMD + M -> Open Menu

# Launch emulator
$ cd $ANDROID_HOME/tools
$ ./emulator -avd <AVD_DEVICE>
$ ./emulator @<AVD_DEVICE>
```



