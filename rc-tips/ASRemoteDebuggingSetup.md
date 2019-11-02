# Android Studio Remote / Wifi Debugging Setup Guide

## 1.0 Get Started

### 1.1 Enable USB Debugging on your RC Phone
To enable the computer to install APK files / open up ADB debug utilities on the phone, you need to activate the USB Debugging on your RC Phone.     
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

### 1.3 Add External Tools to Android Studio

You need to open up Android Studio, open up the FTC project (or you can open up other projects, it doesn't matter)   

**Windows**   
Go to the menu above, click on `File` -> `Settings`.   

**Mac**   
Go to the menu above, click on `Android Studio` -> `Preferences`.   

Then, you need to do the following:   

1. On the Settings / Preferences window that you just opened, enter "External Tools" in the search bar
2. Look on the list on the left. Select the `External Tools` menu item in the `Tools` category.
3. On the right side of the panel, click on `External Tools`, then add several entries listed below.

|Name|Description|Program|Arguments|Working Directory|
|-|-|-|-|-|
|Enable ADB over TCP/IP|Leave Blank|$ModuleSdkPath$/platform-tools/adb|tcpip 5555|$ProjectFileDir$|
|Connect to ADB over TCP/IP|Leave Blank|$ModuleSdkPath$/platform-tools/adb|connect $Prompt$:5555|$ProjectFileDir$|
|Connect to RC over TCP/IP|Leave Blank|$ModuleSdkPath$/platform-tools/adb|connect 192.168.49.1:5555|$ProjectFileDir$|
|Disconnect to ADB over TCP/IP|Leave Blank|$ModuleSdkPath$/platform-tools/adb|disconnect|$ProjectFileDir$|
|Switch ADB back to USB|Leave Blank|$ModuleSdkPath$/platform-tools/adb|-s %Prompt%:5555 usb|$ProjectFileDir$|
|Switch RC back to USB|Leave Blank|$ModuleSdkPath$/platform-tools/adb|-s 192.168.49.1:5555 usb|$ProjectFileDir$|

After adding those external tool entries, save and apply every change, then close the preferences / settings window.   

### 1.4 Connect to Robot Controller

1. Connect your RC phone to your computer via a USB wire, if the RC phone prompts permission request on your phone, click `Yes`.   
2. Open Up Android Studio   
3. If you already have RC installed on your phone, go to the next step, otherwise you need to click the green triangular `Run` button below the menu.   
4. go to the menu on top.   
5. Click on `Tools` -> `External Tools` -> `Enable ADB over TCP/IP`.   
6. Disconnect your phone with your computer.
7. Open up the Robot Controller App on your phone, go to `Program and Manage` page.
8. connect your computer to the phone's Wifi Direct Network given by the information on the `Program and Manage` page.
9. In your Android Studio, go to the menu, and click `Tools` -> `External Tools` -> `Connect to RC over TCP/IP`.
10. The RC might prompt permission request again, select `Yes` (and you can also check the `Always allow this Computer` option before selecting `Yes`.
11. Now you are all set for Wireless Debugging, you can disconnect at any time by going to the menu on top and click `Tools` -> `External Tools` -> `Disconnect to ADB over TCP/IP`.