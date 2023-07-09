

# Amwal Pay Android SDK

Amwal Pay SDK built with flutter makes online payment easier.

## Features
- Payment With Wallet
  - with mobile number
  - with alias name
  - with QRCode
- Payment With Card

## Installation

- Edit `app/build.gradle`

```
android {
  // ...
}

repositories {
  String storageUrl = System.env.FLUTTER_STORAGE_BASE_URL ?: "https://storage.googleapis.com"
  maven {
    url 'https://jitpack.io'
  }
  maven {
    url 'https://storage.googleapis.com/download.flutter.io'
  }
}

dependencies {
  // ...
    debugImplementation 'com.github.amwal-pay.amwal_pay_android_sdk:flutter_debug:1.0'
    releaseImplementation 'com.github.amwal-pay.amwal_pay_android_sdk:flutter_realease:1.0'
}
```

- `FlutterActivity` must be registered in your `AndroidManifest.xml`. Add the following XML to your `AndroidManifest.xml` file under your application tag:
```
<activity
  android:name="io.flutter.embedding.android.FlutterActivity"
  android:theme="@style/LaunchTheme"
  android:configChanges="orientation|keyboardHidden|keyboard|screenSize|locale|layoutDirection|fontScale|screenLayout|density|uiMode"
  android:hardwareAccelerated="true"
  android:windowSoftInputMode="adjustResize"
  />
```
-  import `io.flutter.embedding.android.FlutterActivity`

- start SDK

```
 	button.setOnClickListener {
        val argsList = listOf<String>(  
            "",// token  
            "",// secure hash value  
		    "",// merchant id  
            "",// currency code  
            "",// amount  
            "",// terminalId,  
            "",// isMocked "1" for true and "0" for false  
		    "",// is3DS "1" for true and "0" for false  
		    "",// transaction id  
		    "",// merchant name  
        )
        val myIntent = FlutterActivity.withNewEngine().  
        dartEntrypointArgs(argsList).build(this)
        
	    startActivity(myIntent)  
}
```  
## Issues
If you encounter any issues while using the package, please file a bug report in [the Github issue tracker].

[the Github issue tracker]: <https://github.com/amwal-pay/amwal_pay_android_sdk/issues>
