# NPayFrameworkMC is a framework from 9Pay JSC. Payment solutions, digital service,... are providing by 9Pay's Digital-Wallet.


## Installing

### with [CocoaPods](https://cocoapods.org)
```ruby
use_frameworks!
pod 'NPayFrameworkMC', '~> 1.0.4'

## Usage

At first, import NPayFrameworkMC:

```swift
import NPayFramework
```

The easiest way to start:
```swift
let nLib = NPayManager(vController: self, sdkCfgs: SDKConfigs(merchantCode: "NGuTdi", uid: "uid", brandColor: "-15356318", env: .sandbox))
```

Initial SDKConfigs with merchantCode, uid, brandColor and env(eviroment)

⚠️ Dont forget conform to protocol 'LibListener'

```swift
class ViewController: UIViewController, LibListener {
    func onLoginSuccessfull() {
        //
    }

    func onPaySuccessful() {
        //
    }
    
    func getInfoSuccess(phone: String, balance: String, ekycStatus: String) {
        //
    }
    
    func getMerchantActionSuccess(actions: [String]) {
        //
    }
    
    func onError(errorCode: Int, message: String) {
        
    }
}
```
