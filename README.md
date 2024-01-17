# NPayFrameworkMC 
A framework from 9Pay JSC. Payment solutions, digital service,... are providing by 9Pay's Digital-Wallet.

## Installing

### with [CocoaPods](https://cocoapods.org)
```ruby
use_frameworks!
pod 'NPayFrameworkMC', '~> 2.0.5'
```

## Usage

At first, import NPayFrameworkMC:

```swift
import NPayFramework
```


## Full example

The easiest way to start:
```swift
let merchantCode = "merchant_code" // Contact 9Pay
let secretKey = "secret_key" // Contact 9Pay
let uID = "0975998989" // optional
let brandColor = "15AE62"
let flavorEnv = EnvironmentKey.SANDBOX //  or PRODUCTION

let nLib = NPayManager(vController: self, sdkCfgs: SDKConfigs(merchantCode: merchantCode, secretKey: secretKey, uid: uID, brandColor: brandColor, env: flavorEnv))
```

Initial SDKConfigs with merchantCode, secret key, uid, brandColor and env (environment)

⚠️ Dont forget conform to protocol 'LibListener'

```swift
class ViewControllerDemo: UIViewController, LibListener {
    func getInfoSuccess(user: String) {
        //
    }
    
    func onLogoutSuccessful() {
        //
    }
    
    func onError(errorCode: Int, message: String) {
        //
    }
    
    func onCloseSDK() {
        //
    }
    
    func sdkDidComplete(action: String, status: Bool?, param: [String : Any]?) {
        //
    }
    
    func backToAppFrom(action: String) {
        //
    }
    
}
```

## Config

9Pay SDK needs to use camera for ekyc feature.
Input purpose string into Info.plist of your project

```swift
	<key>NSCameraUsageDescription</key>
	<string>Cho phép ứng dụng truy cập máy ảnh, để có thể chụp hình khi xác thực tài khoản và quét mã vạch thanh toán</string>
	<key>NSPhotoLibraryUsageDescription</key>
	<string>Cho phép ứng dụng ảnh để chọn ảnh mã QR hoặc chụp giấy tờ xác thực</string>
```
