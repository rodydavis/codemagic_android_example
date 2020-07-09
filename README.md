# Native Android with Codemagic

With the introduction of the [Codemagic.yaml](https://docs.codemagic.io/yaml/yaml/) file it is now possible to release any app whether it is built with ReactNative, Flutter, Web, Desktop, iOS or Android! Today we will be setting up an android project from scratch and integrate fastlane into the CLI commands for the yaml file.

## Project Setup

Make sure you have [Android Studio](https://developer.android.com/studio/install) installed and the necessary SDKs you want to release for.

Click “Create a new Android Project” and choose “Basic Activity”:

Now setup your project name and project path:

Now your project should look like this:

## Codemagic Yaml Setup

Now that you have the project setup create a new top level file called `codemagic.yaml` and add the following:

```
workflows:
    android-app:
        name: Android App
        scripts:
            - ./gradlew assembleDebug
        artifacts:
            - build/outputs/**/**/*.apk

```

Check this into VCS and now open the project in Codemagic to run your build!

## Conclusion

Now you can release your application to Google Play Console!