# wm-cordova-cli

A command line untility to build mobile apps created using WaveMaker product.

The main goal of wm-cordova-cli is to simplify generation of APK or IPA for WaveMaker developers. ```wm-cordova-cli``` combines multiple cordova commands into a single command. First, one has to make sure all the required hardware and software are available and installed. Then execute the command with the appropriate values for arguments.


### Cordova versions to use for the build 
1. Based upon the value of 'phonegap-cli' preference value, versions mentioned in the below table are used by default.

| PHONEGAP-CLI | CORDOVA | CORDOVA-ANDROID | CORDOVA-IOS |
|--|--|--|--|
| cli-9.0.0 | 9.0.0 | 8.0.0 | 5.1.1 |
| cli-8.1.1 | 8.1.1 | 7.1.2 | 4.5.5 |
| cli-8.0.0 | 8.0.0 | 7.0.0 | 4.5.4 |

2. In config.xml, the above cordova values can be overridden by setting preferences with the below mentioned names.

    wm-cordova<br>
    wm-cordova-android<br>
    wm-cordova-ios

3. Cordova versions can also be mentioned as command line arguments.



## ANDROID build

### Requirements

-   Linux or MAC
    
-   Latest Android Studio
    
-   Node 10.x ([https://nodejs.org/en/blog/release/v10.18.0/](https://nodejs.org/en/download/))
    
-   GIT ([https://git-scm.com/download/mac](https://git-scm.com/download/mac))
    
-   Java 8
    
-   Gradle 6
    
-   KeyStore file for production release builds
    
-   Install wm-cordova-cli (npm install -g @wavemaker/wm-cordova-cli)
    
-   Make sure JAVA_HOME, ANDROID_SDK and GRADLE_HOME are set in the environment variables and also in PATH.
    

  

### Command

wm-cordova build android <src_dir> <dest_dir> [additional_arguments]

  
  


|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Argument**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| **Description** |
|--|--|
| **src_dir** | **DEFAULT:** current working directory.<br> Path to the cordova zip (or) path to the cordova project folder. |
|**dest_dir**|**OPTIONAL:** Path to the directory where all build files are to be kept.|
|**\-\-cordovaVersion**|**OPTIONAL:** Cordova cli version to use|
|**\-\-cordovaAndroidVersion**|**OPTIONAL:** Version of cordova-ios to use|
|**\-\-aKeyStore**|Absolute path of the key store. If keystore is not given the, android debug is used.|
|**\-\-aStorePassword**|Password to key store|
|**\-\-aKeyAlias**|Alias name of the key|
|**\-\-aKeyPassword**|Key Password|
|**\-\-packageType**|**DEFAULT:** development<br>development or production<br>Use ‘production’ with keystore specified.|

  

### Example 1

~~~
wm-cordova build android "/path/to/src"
~~~
### Example 2    
~~~
wm-cordova build android "/path/to/src" \
--aKeyStore="/path/to/file.keystore" \
--aStorePassword="store_password" \
--aKeyAlias="key_alias_name" \
--aKeyPassword="key" \
--packageType="production"
~~~

## IOS build

### Requirements

-   MAC machine
    
-   Latest XCODE

-   CocoaPods ([https://guides.cocoapods.org/using/getting-started.html#toc_3](https://guides.cocoapods.org/using/getting-started.html#toc_3))
    
-   Node 10.x ([https://nodejs.org/en/blog/release/v10.18.0/](https://nodejs.org/en/download/))
    
-   GIT ([https://git-scm.com/download/mac](https://git-scm.com/download/mac))
    
-   Apple developer or distribution P12 certificates
    
-   Provisioning profile
    
-   Install wm-cordova-cli (npm install -g @wavemaker/wm-cordova-cli)
    

  

### Command

wm-cordova build ios <src_dir> <dest_dir> [additional_arguments]

  
  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Argument**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| **Description** |
|--|--|
| **src_dir** | **DEFAULT:** current working directory.<br> Path to the cordova zip (or) path to the cordova project folder. |
|**dest_dir**|**OPTIONAL:** Path to the directory where all build files are to be kept.|
|**\-\-cordovaVersion**|**OPTIONAL:** Cordova cli version to use|
|**\-\-cordovaIosVersion**|**OPTIONAL:**  Version of cordova-ios to use|
|**\-\-iCertificate**|Absolute path of P12 certificate location|
|**\-\-iCertificatePassword**|Password to unlock the certificate.|
|**\-\-iProvisioningFile**|Absolute path of provisioning file|
|**\-\-packageType**|**DEFAULT:** development<bR>development or production <br>Use ‘production’ with an AppStore distribution certificate.|


### Example

  
~~~
wm-cordova build ios "/path/to/src" \
--iCertificate="/path/to/distribution.p12" \
--iCertificatePassword="unlock_password" \
--iProvisioningFile="/path/to/profile.mobileprovision" \
--packageType="production"
~~~

## License
MIT License
Copyright (c)  2020  WaveMaker
