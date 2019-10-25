# [Darbots-DriverStation-Utilities](https://github.com/DarlingtonProgramming/Darbots-DriverStation-Utilities) Starter Guide

## 1.0 Get Started

### 1.1 Enable USB Debugging on your DS Phone
To enable the computer to install APK files on the phone, you need to activate the USB Debugging on your DS Phone. We highly recommend that you enable the USB Debugging functionality on the RC Phone as well since a lot of times Android Studio Programmers need that functionality for them to write their programs into the RC phone.   
To turn on USB Debugging, first you need to activate Developer Options on your phone. Here are the steps to do so.   

1. Open up `Settings` App
2. Find a tab called `About This Phone` or `This Device`
3. Click 7 times on the System Version Information Tab. As you are clicking, a bulletin should show something like `You are X clicks away from being a developer`
4. Now go to the home page of your settings app, there should be an added tab called `Developer Options`

Now since we have activated Developer Options on our phone, we can enable USB Debugging.   

1. Go to the `Developer Options` tab on your `Settings` APP.
2. Find the switch that says `USB Debugging` on the left side, turn the switch on and we are done!

### 1.2 Install Android Toolchains on Your Computer

#### 1.2.1 Install Platform Tools 
If you have your Android Studio Installed, skip this step, and go to step 1.2.2.   
Download [Android Platform Tools](https://developer.android.com/studio/releases/platform-tools), Unzip them to a folder.   

#### 1.2.2 Make ADB command accessible everywhere

**Windows**   
You need to add your platform-tools folder Path into Your PATH Variable.   

1. open up `Windows Explorer`, right click on `This Computer`, select `Properties`.
2. On the very left of the new page that just showed, click `Advanced System Settings`
3. On the new panel, click `Environment Variables`
4. On the new panel, go to `System Variables` and find `Path` in the list below.
5. Select `Path` and click on `Edit`
6. Here you are going to add a new item that has the URL of your folder `platform-tools`, for example, mine is `D:\APP\Android\SDK\platform-tools\`.
7. Save everything and you are good to go.

**Linux / Mac**   
You need to create a Soft Link / Symbolic Link for your ADB executive file.   

1. Start a shell at your user folder. You can start by either opening up the terminal and type `cd ~\` or right click at the folder and select `start shell here`.
2. Find the `platform-tools` folder, if you are using Android Studio, click on `Tools` -> `SDK Manager`, the `platform-tools` folder will be in your `Android SDK Location`.
3. execute `sudo ln -s PATH_TO_PLATFORM_TOOLS_FOLDER/platform-tools/adb /usr/bin/adb`, it might prompt you to enter your password or so, just do it.
4. If the console said "permission denied", execute `sudo ln -s PATH_TO_PLATFORM_TOOLS_FOLDER/platform-tools/adb /usr/local/bin/adb` instead.
4. You are good to go!

### 1.3 Executing the Script!
Connect your DS phone to the computer via a USB wire. If it prompts permission request on your phone, click `Yes`   
then...   

1. If you have `Windows`, just double click on the `Utilities\install_newest_ds_windows.bat` file.   
2. If you have `Mac` / `Linux`, start shell in the `Utilities Folder` and run `sh install_newest_ds_mac.sh`