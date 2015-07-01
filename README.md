# parse-storyboard-starter
A single view storyboard Xcode project with basic Parse frameworks and initialization code already in place.

The project is a basic single-view application — no different from a blank single-view on Xcode except for the addition of the necessary libraries — except for two additions:

Instructions
------------

1. Clone this repository
2. register for a Parse.com account
3. Create an app on Parse and get your App ID and Client Key
3. Dive into Xcode and have fun!

Setting up Parse in Xcode
-------------------------

In AppDelegate.m’s didFinishLaunchingWithOptions I’ve inserted the necessary Parse initialization code and some boilerplate for Local Datastore and Analytics. The only thing you have to do to get things running is insert your App ID and Client Key (provided by Parse when you set up your app).
```
// [Optional] Power your app with Local Datastore. For more info, go to
// https://parse.com/docs/ios_guide#localdatastore/iOS
[Parse enableLocalDatastore];

// Initialize Parse.
[Parse setApplicationId:@”YOUR-PARSE-APP-ID-GOES-HERE”
clientKey:@”YOUR PARSE-CLIENT-KEY-GOES-HERE”];

// [Optional] Track statistics around application opens.
[PFAnalytics trackAppOpenedWithLaunchOptions:launchOptions];
```
In ViewController.m’s viewDidLoad I’ve inserted code that will test your connection to Parse. By default the code is commented out, but if you uncomment the code and run the app you should see the TestObject class with the row you created in your Parse dashboard. If it doesn’t work, double-check your App ID and Client Keys match those that Parse gave you.
```
PFObject *test = [PFObject objectWithClassName:@”TestObject”];
test[@”foo”] = @”ba”;
[test saveInBackground];
```
That’s it! Dive into Parse’s amazing iOS documentation and see what you can learn.
