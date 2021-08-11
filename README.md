
# react-native-immediate-phone-call-srijan

## Getting started

`$ npm install react-native-immediate-phone-call-srijan --save`

### Mostly automatic installation

`$ react-native link react-native-immediate-phone-call-srijan`

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-immediate-phone-call-srijan` and add `RNReactNativeImmediatePhoneCallSrijan.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNReactNativeImmediatePhoneCallSrijan.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)<

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNReactNativeImmediatePhoneCallSrijanPackage;` to the imports at the top of the file
  - Add `new RNReactNativeImmediatePhoneCallSrijanPackage()` to the list returned by the `getPackages()` method

2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-immediate-phone-call-srijan'
  	project(':react-native-immediate-phone-call-srijan').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-immediate-phone-call-srijan/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-immediate-phone-call-srijan')
  	```
4.For cal permission add this line to manifest.xml in your project for requesting permission of making call 
<uses-permission android:name="android.permission.CALL_PHONE" />

5.add initent-filter under the activity in mainfest.xml file for your project
<application
      android:name=".MainApplication">
      <activity
        android:name=".MainActivity">
          <intent-filter>
              <action android:name="android.intent.action.CALL_PRIVILEGED" />
              <data android:scheme="tel" />
          </intent-filter>
      </activity>
    </application>

## Usage
```javascript
import RNReactNativeImmediatePhoneCallSrijan from 'react-native-immediate-phone-call-srijan';

// TODO: What to do with the module?

const App = () => {
  return (
    <View >
      <Text >
        Call to : +915234567890
      </Text>
      <TouchableOpacity
        onPress={() => RNReactNativeImmediatePhoneCallSrijan.immediatePhoneCall("+915234567890")}
      >
        <Text>Call</Text>
      </TouchableOpacity>
    </View>
  );
};