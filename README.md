# Solved: Unable to load script from assets ‘index.android.bundle’

Follow this

#### 1. Go to your project directory and check if this folder exists android/app/src/main/assets

i) If it exists then delete two files viz index.android.bundle and index.android.bundle.meta

ii) If the folder assets doesn’t exist then create the assets directory there.

#### 2. From your root project directory do
``` bash
cd android
./gradlew clean
```

#### 3. Finally, navigate back to the root directory and check

i) If there is only one file i.e. index.js then run following command
``` bash
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
```
NOTE: That is one single command.

ii) If there are two files i.e index.android.js and index.ios.js then run this
``` bash
react-native bundle --platform android --dev false --entry-file index.android.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
```
This is a single command too!

#### 4. Now run react-native run-android
