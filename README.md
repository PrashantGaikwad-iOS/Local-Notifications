# Local Notifications




import UserNotifications

didFinishLaunchingWithOptions
- requestAuthorization - alert, badge, sound 

ViewDidLoad
Content = UNMutableNotificationContent()
- title
- body
- sound
Trigger = UNTimeIntervalNotification(timeInterval:5,repeats:false)

Request = UNNotificationRequest(identifier:””,content:content, trigger:trigger)

UNNotificationCenter.current().add(request, withCompletionHandler:nil)


For foreground:

AppDelegate:

Implement the delegate = UNUserNotificationDelegate
willPresent notification -{ completionHandler[.alert, .sount] }

To perform some operation - 
didReceive response - { 
if response.notification.request.idenfier == “myIdentifier” {         print(“this is where my logic comes”)
}
completionHandler()
}

didFinishLaunchingWithOptions
UNUserNotificationCenter.current().delegate = self

