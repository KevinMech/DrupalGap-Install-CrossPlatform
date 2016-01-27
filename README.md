# DrupalGap-Install-CrossPlatform

![alt text](https://www.drupal.org/files/project-images/drupalgap-wide.jpg "DrupalGap")

## Setting Up DrupalGap Across Multiple Platforms

**Select your operating system:**

[Windows 7](#windows_7)

[Windows 8](#windows_8)

[Windows 10](#windows_10)

[Mac OSX](#mac_osx)

[Ubuntu](#ubuntu)

**Index:**

1. Install node.js
2. Install Cordova
3. Setup PhoneGap Platforms
4. Install PhoneGap Plugins
5. Install DrupalGap SDK over PhoneGap

## Windows_7

## Windows_8

## Windows_10

## Mac_OSX
### Install XCode
1. Navigate to the [Apple App Store](https://itunes.apple.com/us/app/xcode/id497799835?mt=12) and install XCode.
2. Once installed, run XCode and install all updates.

### Install Homebrew
1. Open Terminal
2. Type this in Terminal:

    ```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

3. Follow the prompts to complete the installation

### Install node.js & npm

1. Install node.js & npm:

    ```bash
$ brew install node
```

2. Check versions to ensure correct installation:

    ```bash
$ node -v
```
    ```bash
$ npm -v
```

3. Update node.js and npm:

    ```bash
$ brew update && brew upgrade node
```

### Install Cordova

1. Install Cordova:

    ```bash
$ npm install -g cordova
```

### Setup PhoneGap Platforms

1. Change directory to desktop:

    ```bash
$ cd ~/Desktop
```

2. Create application files:

    ```bash
$ cordova create ExampleApp com.example "ExampleApp"
```

3. Change to app directory:

    ```bash
$ cd ExampleApp
```

4. Set Paths for the <code>.bash_profile</code>, mine looks like this:

    ```bash
$ export ANDROID_HOME=/home/kyle/android-sdk
$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
$ export PATH=${PATH}:$ANDROID_HOME/platform-tools:$ANDROID_HOME/tools:/usr/share/npm
```

5. Reload <code>.bash_profile</code>:

    ```bash
$ source ~/.bash_profile
```

6. Add Android platform:

    ```bash
$ platform add android
```

7. Build Android platform:

    ```bash
$ cordova build
```

8. Add iOS platform:

    ```bash
$ cordova platform add ios
```

9. Build iOS platform:

    ```bash
$ cordova prepare
```
10. Test the simulators:

    ```bash
$ cordova run
```

### Install PhoneGap plugins

1. Install all PhoneGap plugins:

    ```bash
$ cordova plugin add cordova-plugin-console cordova-plugin-device cordova-plugin-dialogs cordova-plugin-file cordova-plugin-inappbrowser cordova-plugin-network-information cordova plugin add cordova-plugin-camera cordova-plugin-geolocation
```

2. Update your <code>config.xml</code>:

    ```bash
$ cordova plugin save
```

### Install DrupalGap SDK overtop PhoneGap:

1. Click the "download" link on your Drupal site under "Configuration -> Web services -> DrupalGap"
2. Extract the contents of this download into your app's www directory on the desktop (overwrite any files).

    ```
~/Desktop/ExampleApp/www
```

3. Open your app's <code>settings.js</code> file, and switch the mode to phonegap:

    ```
drupalgap.settings.mode = 'phonegap';
```

4. Then include the <code>cordova.js</code> file in the body of your <code>index.html</code> file:

    ```
<!-- Load PhoneGap (Cordova) -->
<script type="text/javascript" src="cordova.js"></script>
```

### Run the App

1. Change to app's root directory:

    ```bash
$ cd ~/Desktop/ExampleApp
```

2. Build and Run the app:

    ```bash
$ cordova build
```
    ```bash
$ cordova prepare
```
    ```bash
$ cordova run
```

### Remove Extra Files

1. Change to app's root directory:

    ```bash
$ cd ~/Desktop/ExampleApp/www
```

2. Delete some extra files:

    ```bash
$ rm -rf css/ img/ js/
```

## Ubuntu

### Install node.js & npm

1. Install node.js:

    ```bash
$ sudo apt-get update
```
    ```bash
$ sudo apt-get install nodejs
```

2. Install npm:

    ```bash
$ sudo apt-get install npm
```

3. Update node.js name for PhoneGap:

    ```bash
$ sudo ln -s /usr/bin/nodejs /usr/bin/node
```

### Install Git

1. Install Git:

    ```bash
$ sudo apt-get install git
```

### Install Ant

1. Install Ant:

    ```bash
$ sudo apt-get install ant
```

### Install PhoneGap

1. Install PhoneGap:

    ```bash
$ sudo npm install -g phonegap
```

2. Install dependencies:

    ```bash
$ sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
```

3. Verify Correct Installation:

    ```bash
$ phonegap -v
```

### Add Android Platform

1. Download the SDK from [here](http://developer.android.com/sdk/index.html) and extract it to <code>/usr/local/android-sdk</code>

    ```bash
$ sudo tar -zxvf ~/Downloads/android-sdk_r24.4.1-linux.tgz -C /usr/local/
```
**Note: This command will change based on the SDK version.**

2. Set Paths:

    ```bash
$ vim ~/.bashrc
```
Add:
    ```bash
export PATH=$PATH:/usr/local/android-sdk-linux/
export PATH=$PATH:/usr/local/android-sdk-linux/tools
export PATH=$PATH:/usr/local/android-sdk-linux/platform-tools
export PATH=$PATH:/usr/local/android-sdk-linux/build-tools
```

3. Reload <code>.bashrc</code>

    ```bash
$ source ~/.bashrc
```
    
4. Verify Correct Installation:

    ```bash
$ android
```

### Install A Faster Emulator (Optional)

1. Install VirtualBox

    ```bash
$ sudo apt-get install virtualbox
```

2. Download the emulator from [here](https://www.genymotion.com/#!/download)
3. Set Permissions:

    ```bash
$ chmod u+x genymotion-2.1.0_x64.bin
$ ./genymotion-2.1.0_x64.bin
```

4. Run the emulator:

    ```bash
$ cd /home/dasunhegoda/Downloads/genymotion/
$ ./genymotion
```

### Create An App

1. Create application files:

    ```bash
$ phonegap create testapp
```

2. Add Android Platform:

    ```bash
$ phonegap platform add android
```

3. Verify the platform was added:

    ```bash
$ phonegap platform -ls
```

4. Run the application:

    ```bash
$ phonegap run android
```
