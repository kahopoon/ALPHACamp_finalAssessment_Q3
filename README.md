# ALPHACamp_finalAssessment_Q3

The App Life Cycle - iOS Developer Library
https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/TheAppLifeCycle/TheAppLifeCycle.html  

From the passage, we can see, apple is talking about how app will interact with the OS - iOS, rather than talking view controller's cycle such as viewDidLoad, viewWillAppear, viewWillDisappear...etc. Make it clear, I am not saying they are not important at the role of app life cycle, but in the documentation, they are responsible for event loops within the app itself, more than interact with the OS, so who is responsible for? In the passage, the answer is appDelegate, from project's appDelegate functions' comments nor the passage above, we can see, they handle event such as user picking calls or sms prompt out...these of system events that concurrently happening with app.  

###Below showing how AppDelegate is communicating with system objects, and also how it connecting between data model and view contollers
![Alt text](screenshot1.png?raw=true "core_ojects_2x")

###Explaining different stage of app at OS environment
![Alt text](screenshot2.png?raw=true "high_level_flow_2x")  
  
OK, let's demonstrate in code, here we have single plage blank app with AppDelegate and ViewController, on all functions of cycle, we print the name of function

## AppDelegate.swift
```swift
import UIKit

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    var window: UIWindow?

    func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
        print("\(#function)")
        return true
    }

    func applicationWillResignActive(application: UIApplication) {
        // Sent when the application is about to move from active to inactive state. This can occur for certain types of temporary interruptions (such as an incoming phone call or SMS message) or when the user quits the application and it begins the transition to the background state.
        // Use this method to pause ongoing tasks, disable timers, and throttle down OpenGL ES frame rates. Games should use this method to pause the game.
        print("\(#function)")
    }

    func applicationDidEnterBackground(application: UIApplication) {
        // Use this method to release shared resources, save user data, invalidate timers, and store enough application state information to restore your application to its current state in case it is terminated later.
        // If your application supports background execution, this method is called instead of applicationWillTerminate: when the user quits.
        print("\(#function)")
    }

    func applicationWillEnterForeground(application: UIApplication) {
        // Called as part of the transition from the background to the inactive state; here you can undo many of the changes made on entering the background.
        print("\(#function)")
    }

    func applicationDidBecomeActive(application: UIApplication) {
        // Restart any tasks that were paused (or not yet started) while the application was inactive. If the application was previously in the background, optionally refresh the user interface.
        print("\(#function)")
    }

    func applicationWillTerminate(application: UIApplication) {
        // Called when the application is about to terminate. Save data if appropriate. See also applicationDidEnterBackground:.
        print("\(#function)")
    }
}
```

## ViewController.swift
```swift
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        print("\(#function)")
    }

    override func viewDidAppear(animated: Bool) {
        print("\(#function)")
    }
    
    override func viewWillAppear(animated: Bool) {
        print("\(#function)")
    }
    
    override func viewDidDisappear(animated: Bool) {
        print("\(#function)")
    }
    
    override func viewWillDisappear(animated: Bool) {
        print("\(#function)")
    }
    
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }

}
```
