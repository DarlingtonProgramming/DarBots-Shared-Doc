# Streaming RobotController Screen
This tutorial teaches you on how to set up a phone-to-computer streaming over ADB debugging bridge in FTC software development.   

## 1.0 Set up wireless connection / remote debugging.
Please follow the guide in [Android Studio Remote / Wifi Debugging Setup Guide](ASRemoteDebuggingSetup.md)   

## 2.0 Install Scrcpy Software on your computer.
### 2.1 Windows Setup
#### 2.1.1 Downloading The Project
Download the Scrcpy Software in the link below   
[Win32 - V1.10](https://github.com/Genymobile/scrcpy/releases/download/v1.10/scrcpy-win32-v1.10.zip)   
[Win64 - V1.10](https://github.com/Genymobile/scrcpy/releases/download/v1.10/scrcpy-win64-v1.10.zip)
#### 2.1.2 Starting a shell
1. Unzip the file you just downloaded to a folder that you can find every time. For example, I had it `D:\APP\scrcpy`.
2. Press the `Windows + R` key on your keyboard, on the window that showed up, type `cmd` and press enter
3. type your disk character in the commend prompt followed by a `:`, for example, I have `D:`, then press enter
4. type `cd YOUR_PATH_TO_SCRCPY`, for example, mine is `cd D:\APP\scrcpy\`

### 2.2 Mac Setup
#### 2.2.1 Installing Homebrew
1. Open up `Terminal` on your mac, if you don't know how to find it, it should be in a folder called `Other` in your `LaunchPad`.
2. To verify if you have homebrew installed or not, type `brew --version`, then press enter, if a text like `Homebrew X.X.X` does not show up, follow the instructions below, otherwise skip this step and go to step 2.2.2
3. Type in `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"` and press enter. During the installation process the command prompt might ask you several times for your password, just time them in and press enter.

#### 2.2.2 Installing scrcpy and platform tools
1. If you don't have Android Studio on your mac, type in `brew cask install android-platform-tools` and press enter, otherwise follow step 1.2.2 in [Darbots-DriverStation-Utilities Starter Guide](ds-utilities/README.md).
2. type in `brew install scrcpy` and press enter.

## 3.0 Use scrcpy software on your computer.
1. type `scrcpy -b2M -m800` and press enter, the contents on your phone should start streaming.