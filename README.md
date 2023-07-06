# GimbalTestProj
Seeing error when attempting to launch ios emulator for development

```
The following build commands failed:
         CompileC /Users/[redacted]/Library/Developer/Xcode/DerivedData/rtsproshell-cnnwekjxfvtoftcwymswfzhsqlrd/Build/Intermediates.noindex/Pods.build/Debug-iphonesimulator/rtn-gimbal-airship-adapter.build/Objects-normal/x86_64/GimbalService.o /Users/[redacted]/dev/rtspro-mobile/node_modules/rtn-gimbal-airship-adapter/ios/GimbalService.m normal x86_64 objective-c com.apple.compilers.llvm.clang.1_0.compiler (in target 'rtn-gimbal-airship-adapter' from project 'Pods')
(1 failure)
 
...
 
/Users/[redacted]/dev/rtspro-mobile/node_modules/rtn-gimbal-airship-adapter/ios/GimbalService.m:41:31: error: property 'delegate' not found on object of type 'AirshipAdapter *'
        AirshipAdapter.shared.delegate = self;
                              ^
```

## Steps to reproduce
1. Clone repo
2. `npm install`
3. `cd ios && pod install && cd ..`
4. `npx react-native run-ios`

## Repo Contents
A test repo for demonstraiting the above issue. Was created using the following:

1. `npx react-native@0.69.11 init GimbalTestProj --version 0.69.11`
2. `cd GimbalTestProj`
3. `npm install rtn-gimbal-airship-adapter@1.1.0 "@ua/react-native-airship"@15.2.1`
4. Updates to [App.js](App.js) to import/mount the above dependencies
  - Lines 29-47
