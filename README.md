# DrupalGap-Install-CrossPlatform

![alt text](https://www.drupal.org/files/project-images/drupalgap-wide.jpg "DrupalGap")

## Setting Up DrupalGap across multiple platforms

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
