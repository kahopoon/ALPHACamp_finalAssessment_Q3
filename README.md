# ALPHACamp_finalAssessment_Q3

The App Life Cycle - iOS Developer Library
https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/TheAppLifeCycle/TheAppLifeCycle.html  

From the passage, we can see, apple is talking about how app will interact with the OS - iOS, rather than talking view controller's cycle such as viewDidLoad, viewWillAppear, viewWillDisappear...etc. Make it clear, I am not saying they are not important at the role of app life cycle, but in the documentation, they are responsible for event loops within the app itself, more than interact with the OS, so who is responsible for? In the passage, the answer is appDelegate, from project's appDelegate functions' comments nor the passage above, we can see, they handle event such as user picking calls or sms prompt out...these of system events that concurrently happening with app.  

Below showing how AppDelegate is communicating with system objects, and also how it connecting between data model and view contollers
![Alt text](core_objects_2x.png?raw=true "core_ojects_2x")

Explaining different stage of app at OS environment
![Alt text](high_level_flow_2x.png?raw=true "high_level_flow_2x")
