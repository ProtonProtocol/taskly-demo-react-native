# Taskly

This is a demo app for using the [https://www.npmjs.com/package/@proton/react-native-sdk](Proton React Native SDK)

The project uses Typescript and is was started with a template from https://github.com/infinitered/ignite

This project does not use Expo(https://expo.io/).

# Requirements (Android)

Requirements:

1. Install Android Studio (It was tested with version 4.1.1), [https://www.oracle.com/java/technologies/javase/15-relnote-issues.html](JDK v15).
2. Follow the setting up instructions on https://reactnative.dev/docs/environment-setup for the section `Installing dependencies`
3. In Android Studio, select "Open an Existing Project" and select `/android`
4. Android Studio may ask to install some additional dependencies.
5. If there is an "Upgrade Gradle" dialog that pops up, DO NOT do this. This might break the build.
6. Click the phone icon on the top right and add a virtual device to test with a simulator.
7. Specify the location of the Android SDK by making a new file `local.properties` in the root of the `android` folder with the contents (for Macs): `sdk.dir = /Users/[your username]/Library/Android/sdk` or the path that the Android SDK was installed for your device.

We use Node version v10 to v11. Make sure [https://nodejs.org/en/](Node) and [https://yarnpkg.com/]Yarn are installed.

Installation of the app:

`git clone`

`yarn`

To run the app on the simulator:

1. Start the react-native dev server by running `yarn start`. Keep that window open.
2. Open a simulator in Android Studio by clicking on the phone in the top bar and then selecting the phone and clicking the launch button.
3. In the console run `yarn android` and the application should be installed to your phone.

For running the app on a real device do the same steps as above, but instead of opening the simulator connect your phone with USB to your computer and make sure you have enabled USB debugging.

In certain environments, there may be an issue with the Gradle version number. This error may pop up in the console when running `yarn start` or `yarn android`: 
```
java.lang.NoClassDefFoundError: Could not initialize class org.codehaus.groovy.vmplugin.v7.Java7
```

If this is the case, you must upgrade the Gradle version to 6.3 in `/android/grade/wrapper/grade-wrapper.properties`. Change the version like so:
```
distributionUrl=https\://services.gradle.org/distributions/gradle-6.3-all.zip
```

## Building a Release build for Android (apk)

To build and apk that does not need a Javascript server to connect to, run the following commands:

1. `cd android` (go to the android folder)
2.  `./gradlew assembleRelease ` (build the apk)

After those commands you should be able to find the apk under ./app/build/outputs/apk/release/app-release.apk


# Requirements (iOS)

Since this project is an iOS App, a Mac is necessary.

Install the following requirements.

1. Install XCode and make sure you have version (12.2).
2. Install the Xcode command line tools by runnning `xcode-select --install` in the terminal
3. Install CocoaPods (https://cocoapods.org/) by running `sudo gem install cocoapods`
4. Install homebrew by follwing the instructions on https://brew.sh/.
5. Run `brew install watchman` to install watchman

We use Node version v10 to v11. Make sure [https://nodejs.org/en/](Node) and [https://yarnpkg.com/]Yarn are installed.

To run the app on a simulator:
1. open ios/TasklyIos.xcworkspace/
2. select "Taskly iOS Develop" scheme
3. select "iPhone 11" as a simulator
4. Click the run button

The first time the app builds can take quite some time (maybe 10 minutes) depending on the number of cores and other functionality. While the app is building, a new terminal will popup that has the dev server running. Please do not close this window while the simulator is running.

When you want to run on a physical device, open Xcode and click on Preferences and add your account there.

Next connect your iPhone with a cable to your computer. Then run the following commands:

1. open ios/TasklyIos.xcworkspace/
2. select "Taskly iOS Develop" scheme
3. select "YourName's Phone"
4. Click the run button

You should be able to run it on your phone.

[![CircleCI](https://circleci.com/gh/infinitered/ignite-bowser.svg?style=svg)](https://circleci.com/gh/infinitered/ignite-bowser)

## Environment variables

To change the chain that the demo is connected to change the .env file. The current value of .env file is equal to the content of .env.production. There is an additional file .env.local for the test environment.
