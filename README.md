<h1 align="center"> ANDROID INTERVIEW 2022 </h1>
<p align="center">
  <a href="https://github.com/facebook/react-native/blob/HEAD/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="React Native is released under the MIT license." />
  </a>
  <a href="https://reactnative.dev/docs/contributing">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome!" />
  </a>
</p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)

## 👇 Overview

## 🚀 Question ##

### [Q1]: What are four Android Components?
1. Activities
2. Services
2. Broadcast receivers
4. Content Providers
- - - - 
### [Q2]: What are types of Permissions?
- Answer with 2 permissions: (3đ):
    - Normal permissions
    - Runtime permissions
- Give examples (4đ)    
- Answer with full permissions (5đ)
    - Install-time permissions
    - Normal permissions
    - Signature permissions
    - Runtime permissions
    - Special permissions
- - - - 
### [Q3]: Trong Android có những cách lưu trữ dữ liệu nào?
Trả lời được 2 ý này thì cho(3đ)
- External file storage: Lưu trữ tập tin trên hệ thống tập tin chia sẻ ra được bên ngoài. Thường dùng cho các tập tin mà người dùng được chia sẻ, chẳng hạn như hình ảnh, video.
- Shared Preferences: Lưu trữ dữ liệu nguyên thủy bởi các cặp key-value.
Trả lời và giải thích được khác nhau giữa External file storage và Internal file storage (4đ)
- Internal file storage: Lưu trữ các tập tin riêng tư của ứng dụng (app-private files) trong hệ thống file của thiết bị.
Trả lời được thêm 1 ý này thì cho 5đ
- Database: Lưu trữ các dữ liệu có cấu trúc trong cơ sở dữ liệu private.
- - - -
### [Q4]: What are the major activity states?

[X] onCreate(), onStart(), onResume(), onPause(), onStop(), and onDestroy()

- Running/Active (Đang chạy): when there is an ongoing activity.
- Pause (Tạm dừng): When it is running in the backgroud and is visible to the user.
- Stop (Dừng lại): When it is obscured by another.
- Dead/Destroyed (Kết thúc): When the activity is killed.
- - - -

### [Q5]: What is an Intent?
1. It is a kind of message or information that is passed to the components. It is used to launch an activity, display a web page, send SMS, send email, etc. There are two types of intents in android: 
- Implicit Intent
- Explicit Intent
- - - -
### [Q6]: Có mấy loại Intent chính trong Android?
- Implicit Intent – Intent không tường minh: là khi tạo một đối tượng Intent sẽ chỉ truyền vào action và gửi cho Android. Android sẽ dựa vào action đó mà lọc những thành phần nào đã đăng kí action đó gọi ra. Vì vậy, Android có thể tự động kích hoạt thành phần từ cùng một ứng dụng hoặc một số ứng dụng khác để xử lý intent đó.
- Explicit Intent – Intent tường mình tức là khi tạo một đối tượng Intent, chúng ta chỉ định rõ và truyền trực tiếp tên thành phần đích vào intent.
- - - -
### [Q7]: Pending Intent?
- Frequently Used In: NotificationManager, AlarmManager, AppWidgetManager
- Stars at some point in the future
### [Q8]: Intent?
- Stars immediately

### [Q9]: What are 4 launch modes in Android?
- standard (default): A -> B -> C -> D -> C (2 instances of Activity C)
- singleTop: 
    - A -> B -> C -> D launch D (singleTop) (only 1 D instance, onNewIntent will be call)
    - A -> B -> C -> D launch C (singleTop) <i>C is launched again as its not at the top of the task.</i>
- singleTask:
    - A -> B(singleTask) -> C -> D launch B to A -> B: <i>We can see that the C and D instances are removed from the stack and the information is routed through onNewIntent()
</i>
- singleInstance

- - - -
### [Q10]: Broadcast Receive?
Android apps can send or receive broadcast messages from the Android system and other Android apps, similar to the publish-subscribe design pattern. These broadcasts are sent when an event of interest occurs. For example, the Android system sends broadcasts when various system events occur, such as when the system boots up or the device starts charging. Apps can also send custom broadcasts, for example, to notify other apps of something that they might be interested in (for example, some new data has been downloaded).

Apps can register to receive specific broadcasts. When a broadcast is sent, the system automatically routes broadcasts to apps that have subscribed to receive that particular type of broadcast.

- - - -
### [Q11]: What is Dependency Injection Pattern?
Dependency Injection pattern is where if our object requires other object, it will be passed to our object instead of us having to create that object. This other object is called as dependency.

- - - -
### [Q12]: What is Service Locator Pattern?
Service Locator Pattern uses central Registry known as Service Locator which upon request provides objects for our class. This pattern has severe criticism that its an Anti-Pattern.

- - - -
### [Q13]: How SharedPreferences work internally?
- Shared Preferences are XML files to store private primitive data in key-value pairs. Data Types include Booleans, floats, ints, longs, and strings.
- Shared preferences internally has an in-memory storage on top of disk storage. Every operation goes through in-memory storage first and then to the disk if necessary.
- apply(): Unlike commit, which writes its preferences out to persistent storage synchronously apply commits its changes to the in-memory immediately but starts an asynchronous commit to disk and you won't be notified of any failures. 

- - - -
### [Q14]: Internal implementation of RecyclerView
- 4 major components of RecyclerView
  - Adapter
  - LayoutManager
  - ItemAnimator
  - ViewHolder
- When a view scrolls out of sight and is no longer displayed, it becomes a scrap view.
- When a new item is to be displayed, a view is taken from the recycle pool for reuse. Because this view must be re-bound by the adapter before being displayed, it is called a dirty view.
- The dirty view is recycled: the adapter locates the data for the next item to be displayed and copies this data to the views for this item. References for these views are retrieved from the recycler view’s view holder.
- The recycled view is added to the list of items in the RecyclerView that is about to go on-screen.
- The recycled view goes on-screen as the user scrolls the RecyclerView to the next item in the list. Meanwhile, another view scrolls out of sight and is recycled according to the above steps.
- - - -
### [Q15]: App StartUp, what happen when app launched?
1. createAppContext: Loading the application binary into memory
2. makeApplication : Create Application class and init class attributes
3. installContentProvider: Instantiate and call onCreate for content providers
4. callApplicationOnCreate: call Application onCreate method
5. newActivity: Create activity class and init class attributes
6. attach: Attach context to the activity
7. performOnCreate: call activity.onCreate method

https://medium.com/@lucas.nelaupe/android-app-start-explained-6b20d6700238

### [Q16]: Given two fragments in an activity. If we click on a button in Fragment 1, a counter should increment on Fragment 2.
--> Answered: Taking an interface and an activity will implement that interface. A typical android interview question.
- - - -
### [Q17]: If a dialog fragment is launched on an activity, what life cycle methods will be called on activity.
--> Answered: OnStop will be called.
- - - -
### [Q18]: What is a Content Provider?
Mechanism for providing or exchanging content between different applications.

### [Q19]: What is a Content Provider?
What are the activity lifecycle methods that trigger when user navigate from ActivityA to ActivityB?
A — onPause
B — onCreate
B — onStart
B — onResume
A — onStop

### [Q20]: Can not categories?
- Avoid non-static inner classes in Activities. Use static inner classes with weak
references so they can not be GC-ed when they are not used.
- - - -
### [21]: What does the word static mean in java?
- A member of a class can be accessed without instantiating an object of its class.
- Overriding is based on dynamic binding at runtime, static members are bound at compile-time
- - - -
### [22]: What lifecycle methods will trigger when FragmentB is added on top of FragmentA?
B-> onAttach
B-> onCreate
B-> onCreateView
B-> onActivityCreated
B-> onStart
B-> onResume
- - - -
### [23]: What lifecycle methods will trigger when FragmentB is pop-backed??
B-> onPause
B-> onStop
B-> onDestroyView
B-> onDestroy
B-> onDetach
- - - -
### [24]: Explain ViewPaper2
ViewPager2 supports paging through a modifiable collection of fragments, calling notifyDatasetChanged() to update the UI when the underlying collection changes. This means that your app can dynamically modify the fragment collection at runtime, and ViewPager2 will correctly display the modified collection
- - - -
### [25]: What are some of the features which are there in Kotlin but not In Java?
Lambda expressions + Inline functions = performant custom control structures.
Extension functions.
Null-safety.
Smart casts.
String templates.
Properties.
Primary constructors.
First-class delegation.
- - - -
### [26]: What are Coroutines? and how many types of coroutines?
Coroutines is a new way of writing asynchronous, non-blocking code. An asynchronous code (from asynchronous programming) is code that runs parallel to others. It is also called non-blocking since it does not block the main thread. Asynchronous programming helps in running multiple unrelated tasks faster
- - - -
### [27]: What is an infix function in Kotlin?
Functions marked with infix keyword can also be called using infix notation means calling without using parenthesis and dot.
There are two types of infix function notation in Kotlin-
Standard library infix function notation
User-defined infix function notation
- - - -
### [28]: What is the difference between signed apk and apk bundle?
App Bundles are a publishing format,
whereas APK (Android application PacKage) is the packaging format that eventually will be installed on the device.
App Bundles use bundletool to create a set of APK. (.apks) This can be extracted and the base and configuration split as well as potential dynamic feature modules can be deployed to a device.
- - - -
### [29]: What is a JobScheduler?
This is an API for scheduling various types of jobs against the framework that will be executed in your application’s own process
This is commonly called batch scheduling, as the execution of non-interactive jobs is often called batch processing, though traditional jobs and batch are distinguished and contrasted.
- - - -
### [30]: Explain ANRAA?
When the UI thread of an Android app is blocked for too long, an “Application Not Responding” (ANR) error is triggered. If the app is in the foreground, the system displays a dialog to the user, as shown in figure 1. The ANR dialog gives the user the opportunity to force quit the app

## ⚙️ Copyright
```
Created by $username on $today
Copyright (c) $today.year . All rights reserved.
Last modified $file.lastModified
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)

## 👇 Authors
<p>
    <a href="https://nphau.medium.com/" target="_blank">
    <img src="https://avatars2.githubusercontent.com/u/13111806?s=400&u=f09b6160dbbe2b7eeae0aeb0ab4efac0caad57d7&v=4" width="96" height="96">
    </a>
</p>