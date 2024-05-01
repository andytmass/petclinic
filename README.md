# Pet Clinic as Tutorial

If you are also looking for a simple but end to end fully functional tutorial, including database, sql, Spring, Flutter, here is the right place for you. 

This tutorial also provides step by step instruction to help reads with little previous experience to follow and try out your first simple but working application. 


## Software requirements

- Operating system
  - macOS 14+
  - Windows(?)

- Dev Tools 
  - Git 2.27+
  - JDK 17+
  - Flutter SDK
  
- Android
  - Android Studio 2023.1 (Hedgehog)+
  - Flutter plugin for IntelliJ

- iOS
  - Xcode 15+
  - CocoaPods 1.13+

## Step by step

- Dev Tools
  - Git 2.27+
    - Check Git version
      - ```
        git --version
        git version 2.39.3 (Apple Git-145)
        ```
    - Install Git
      - ```
        brew install git
        ```
    - You might need to re-install homebrew to get brew/git installed properly
  - JDK 17+
    - Check JDKs
      - ```
        java -version
        /usr/libexec/java_home -V
        ```
    - Install
      - Download from [Azul Zulu](https://www.azul.com/downloads/?package=jdk#zulu), select Java 17 (LTS)
      - Install downloaded dmg
    - In ~/.zshrc, add
      ```
      export JAVA_HOME=$(/usr/libexec/java_home -v 17.0.10)
      ```
    - Check JDKs again
      ```
      source ~/.zshrc
      java -version
      echo $JAVA_HOME
      ```

  - Flutter SDK
    - Install
      - [Download](https://docs.flutter.dev/get-started/install/macos/mobile-ios?tab=download)
        - [Intel Processor](https://storage.googleapis.com/flutter_infra_release/releases/stable/macos/flutter_macos_3.19.5-stable.zip)
        - [Apple Silicon](https://storage.googleapis.com/flutter_infra_release/releases/stable/macos/flutter_macos_arm64_3.19.5-stable.zip)
      - Create a folder where you can install Flutter.
        - Consider creating a directory at `~/development/`.
      - Extract the zip file into the directory you want to store the Flutter SDK.
        ```
        # Intel cpu
        unzip ~/Downloads/flutter_macos_3.19.5-stable.zip -d ~/development/
        
        # Apple Silicon cpu
        unzip ~/Downloads/flutter_macos_arm64_3.19.5-stable.zip -d ~/development/
        ```
    - Add Flutter to your PATH
      - Copy the following line and paste it at the end of your ~/.zshrc file. 
        ```
        export PATH=$HOME/development/flutter/bin:$PATH
        ```
      - check installed flutter version
        ```
        source ~/.zshrc
        # check version
        flutter --version
        ```

- Android Studio
  - [Android Studio 2023.1 (Hedgehog)+](https://developer.android.com/studio/install)
    - [Download the latest version of Android Studio.](https://developer.android.com/studio)
  - [Flutter plugin for IntelliJ](https://plugins.jetbrains.com/plugin/9212-flutter)
    - Open Android Studio
    - Settings
    - Plugins
    - Flutter -> Install
    - Dart -> Install
    - Restart IDE

- [Configure Android development](https://docs.flutter.dev/get-started/install/macos/mobile-android#configure-android-development)
  - [Configure Android toolchains](https://docs.flutter.dev/get-started/install/macos/mobile-android?tab=later-start#configure-the-android-toolchain-in-android-studio). 
    - Launch Android Studio.  Follow the Android Studio Setup Wizard. Install the following components:
      - File -> Settings -> Android SDK
      - SDK Platforms
        - Android SDK Platform, API 34.0.0
      - SDK Tools
        - Android SDK Command-line Tools
        - Android SDK Build-Tools
        - Android SDK Platform-Tools
        - Android Emulator
  - Configure your target Android device, following [this](https://docs.flutter.dev/get-started/install/macos/mobile-android#set-up-the-android-emulator)
  - [Agree to Android licenses](https://docs.flutter.dev/get-started/install/macos/mobile-android#agree-to-android-licenses)
    ```
    flutter doctor --android-licenses
    ```
- [Configure iOS development](https://docs.flutter.dev/get-started/install/macos/mobile-ios#configure-ios-development)
  - [Xcode 15+](https://developer.apple.com/xcode/)
    - Install [Xcode 15+](https://developer.apple.com/xcode/)
      - Check version
      ```
      xcodebuild -version
      ```
    - Configure Xcode
      - To configure the command-line tools to use the installed version of Xcode, run the following commands.
        ```
        sudo sh -c 'xcode-select -s /Applications/Xcode.app/Contents/Developer && xcodebuild -runFirstLaunch'
        ```
      - Sign the Xcode license agreement.
        ```
        sudo xcodebuild -license
        ```
    - Configure your iOS simulator
      - To install the iOS Simulator, run the following command.
        ```
        xcodebuild -downloadPlatform iOS
        ```
      - To start the Simulator, run the following command:
      ```
       open -a Simulator
      ```
  - [CocoaPods 1.13+](https://guides.cocoapods.org/using/getting-started.html#installation)
    - Check CocoPods installed version
      ```
      pod --version
      ```
    - Install cocoapods following [the CocoaPods install guide](https://guides.cocoapods.org/using/getting-started.html#installation).
      - ```
        sudo gem install cocoapods
        ```
    - Check pod version
      ```
      gem which cocoapods
      ```
    - Copy the following line and paste it at the end of your ~/.zshrc file.
      - ```
        export PATH=/opt/homebrew/lib/ruby/gems/3.2.0/bin:$HOME/.gem/bin:$PATH
        ```

- Check your development setup
  - ```
     flutter doctor

    ```
## Running this project locally

- Clone this repo
  ```
  # mkdir -p ~/code/
  git clone https://github.com/tonytmass/petclinic.git
  ```

- Start Backend
  - ```
    cd petclinic/backend
    ./mvnw spring-boot:run
    ```
  - A REST back-end should running at localhost at http://localhost:9966/petclinic.
    Get your server address and update petclinic.yaml to your base application address and user credentials.
- Open 

## Resources to get started with this first Flutter project:
- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

## Credits
- [spring-petclinic-rest](https://github.com/spring-petclinic/spring-petclinic-rest)
- [flutter-petclinic](https://github.com/lepidopterists/flutter-petclinic)