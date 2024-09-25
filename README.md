Common
1. OOPS Concept
OOPS stands for Object-Oriented Programming, consisting of four key concepts:

Encapsulation: Wrapping data and methods into a single unit (class).
Inheritance: One class acquires the properties of another class (extends keyword in Java/Kotlin).
Polymorphism: Ability to take many forms. Achieved via method overloading and overriding.
Abstraction: Hiding implementation details and showing only functionality (using abstract classes or interfaces).

Example:

open class Animal {
    open fun sound() {
        println("Animal makes a sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("Dog barks")
    }
}
2. Multiple Inheritance in Android
Java/Kotlin does not support multiple inheritance to avoid ambiguity. However, multiple inheritance is achieved using interfaces.

Example:

interface Movable {
    fun move()
}

interface Flyable {
    fun fly()
}

class Bird : Movable, Flyable {
    override fun move() {
        println("Bird is moving")
    }

    override fun fly() {
        println("Bird is flying")
    }
}
3. What is Abstract Class?
An abstract class is a class that cannot be instantiated and may contain abstract methods (methods without a body).

Example:

abstract class Shape {
    abstract fun draw()
}

class Circle : Shape() {
    override fun draw() {
        println("Drawing Circle")
    }
}
1. Explain Activity Lifecycle
Activity lifecycle includes the following methods:

onCreate(): Called when the activity is first created.
onStart(): Called when the activity becomes visible.
onResume(): Called when the activity starts interacting with the user.
onPause(): Called when the activity is partially obscured.
onStop(): Called when the activity is no longer visible.
onRestart(): Called after the activity is stopped, prior to being started again.
onDestroy(): Called before the activity is destroyed.

Example:

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    // Activity initialization code
}
2. Explain Fragment Lifecycle
Fragment lifecycle includes:

01. onAttach()
Called when the fragment is first attached to its parent activity. Use this to obtain a reference to the activity or context.

02. onCreate()
Called when the fragment is being created. Used to initialize non-UI components like data or saved states.

03. onCreateView()
Called to inflate the fragment's layout. It returns the root view of the fragment's UI.

04. onActivityCreated()
Called when the host activity's onCreate() has completed. Useful for final UI setup and interacting with the activity.

05. onStart()
Called when the fragment is visible to the user. You can set up observers or register components here.

06. onResume()
Called when the fragment is active and interacting with the user. This is where you handle UI interactions.

07. onPause()
Called when the fragment is partially obscured. Use it to pause ongoing tasks (e.g., animations, sensors).

08. onStop()
Called when the fragment is no longer visible. Useful for stopping background processes or saving data.

09. onDestroyView()
Called when the view hierarchy of the fragment is being destroyed. Clean up view references to avoid memory leaks.

10. onDestroy()
Called to perform any final cleanup of the fragment’s state, such as releasing resources.

11. onDetach()
Called when the fragment is detached from the parent activity. Typically used for cleanup related to the activity's context.

Example:

override fun onCreateView(
    inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?
): View? {
    return inflater.inflate(R.layout.fragment_example, container, false)
}
3. What is Context?
Context is the handle to system resources, such as databases, preferences, and UI.

Example:

val sharedPreferences = context.getSharedPreferences("MyPrefs", Context.MODE_PRIVATE)
4. What are the Building Blocks of Android?
Activity
Service
Broadcast Receiver
Content Provider

5. Which is the Non-SQL Database in Android?
Realm and Firebase Realtime Database are popular NoSQL databases for Android.

6. What is ADB?
ADB stands for Android Debug Bridge. It is a command-line tool to communicate with Android devices/emulators.

7. What is ANR?
ANR stands for Application Not Responding. It happens when an application takes too long (over 5 seconds) to respond to user input.

8. What is a Singleton?
A Singleton is a design pattern where only one instance of a class is created.

Example:

object Singleton {
    fun doSomething() {
        println("Singleton instance")
    }
}
9. What is AndroidManifest file?
It is an XML file that contains essential information about the app, such as permissions, activities, services, etc.

10. What is Content Provider in Android?
Content providers manage access to shared data like contacts or images, and allow apps to query or modify the data.

11. Difference between Service and Thread?
Service: A component that runs in the background, performing long-running operations.
Thread: A low-level component for concurrent execution inside the same process.

12. Difference between compileSdkVersion and targetSdkVersion?
compileSdkVersion: The Android API level used to compile the app.
targetSdkVersion: The Android API level the app is designed to run on.

13. What is JobScheduler?
JobScheduler is an API for scheduling background tasks in Android.

14. What is Retained Fragment?
A retained fragment allows fragment data to be retained across configuration changes.

15. Difference between LiveData and MutableLiveData?
LiveData: Observable data that cannot be changed externally.
MutableLiveData: A subclass of LiveData that allows data modification.

16. Example when Activity's onRestart method is called?
It is called when the activity comes back to the foreground after being stopped, like when returning from another activity.

17. What are the Types of Intent? (with example)
Explicit Intent: Used to launch a specific component.
Implicit Intent: Used to perform general actions like sharing data.

Example:

val intent = Intent(this, SecondActivity::class.java)
startActivity(intent) // Explicit intent
18. Types of Service?
Foreground Service
Background Service
Bound Service

19. What is Socket? How to connect with socket?
A socket is an endpoint for communication. In Android, use Socket class to create a connection.

Example:

val socket = Socket("serverAddress", portNumber)
20. What is Gradle File?
Gradle is a build system that manages dependencies, compiles code, and packages the app.

21. Difference between ViewBinding and DataBinding?
ViewBinding: Easier, faster view reference binding.
DataBinding: More advanced, allows binding expressions and two-way data binding.

22. Difference between commit and apply in SharedPreferences?
commit(): Synchronous and returns a boolean value.
apply(): Asynchronous and does not return a value.

23. What are Dangerous Permissions?
Permissions that involve sensitive user data like location, contacts, or camera.

24. What are Signature Permissions?
Permissions granted only if the requesting app is signed with the same certificate as the app defining the permission.

25. Types of Sensors Available in Android?
Accelerometer
Gyroscope
Proximity sensor

26. What is Broadcast Receiver?
A component that listens for and responds to system-wide broadcast announcements.

27. What is Notification Channel? (API levels)
From API 26 (Android 8.0), notifications must be assigned to a channel to display.

28. Primitive and Non-Primitive Data Types?
Primitive: int, float, boolean, etc.
Non-Primitive: String, Arrays, Classes.

29. What is a Higher-Order Function?
A function that takes another function as a parameter or returns a function.

30. Types of Launch Modes in Android?
Standard
SingleTop
SingleTask
SingleInstance

31. When ANR occurs and how to prevent it?
ANR happens when the main thread is blocked. Prevent it by using background threads for long-running tasks.

32. Which Method is Called Only Once in a Fragment Lifecycle?
onAttach() and onDetach().

33. Difference between Serializable and Parcelable?
Serializable: Simpler but slower.
Parcelable: Android-specific, faster for passing data.

34. Difference between Service and IntentService?
Service: Runs on the main thread.
IntentService: Runs on a background thread.

35. What is Dependency Injection?
A design pattern used to inject dependencies into a class, making it more modular and testable. Popular frameworks: Dagger, Hilt.

36. What is AsyncTask?
AsyncTask was used for background operations but has been deprecated due to inefficiency in managing background tasks.

37. Alternative for AsyncTask?
Use Executors, Coroutines, or WorkManager.

38. Difference between Support Fragment Manager and Child Fragment Manager?
Support Fragment Manager: Manages parent fragments.
Child Fragment Manager: Manages child fragments inside a parent fragment.

39. Types of View Animations?
Tween Animation
Frame Animation
Property Animation

Kotlin
01. Why choose Kotlin over Java?
Kotlin offers several advantages over Java:

Conciseness: Kotlin reduces boilerplate code significantly.
Null Safety: Kotlin has built-in null safety, reducing NullPointerException risks.
Interoperability: Kotlin is 100% interoperable with Java, meaning you can use both in the same project.
Coroutines: Kotlin supports coroutines for asynchronous programming, which simplifies managing background threads.
Smart Casts: Kotlin automatically casts variables without requiring explicit checks.

Example: Null safety in Kotlin:

val name: String? = null  // Nullable type
val length = name?.length ?: 0  // Uses the Elvis operator to provide a default value
02. What is the difference between val and var keywords?
val: Immutable reference, similar to final in Java. Once assigned, its value cannot change.
var: Mutable reference. Its value can be changed after initialization.

Example:

val name = "Kotlin"  // Immutable
var age = 25         // Mutable
03. What are the scoped functions in Kotlin?
Kotlin provides several scoped functions to work with objects in concise and readable ways:

let: Executes a block of code and returns its result.
run: Executes a block and returns the last expression.
apply: Modifies the receiver and returns the object itself.
also: Similar to apply but for additional actions.
with: A non-extension function used for context object access.

Example:

val result = "Kotlin".let {
    it.uppercase()
}
println(result) // KOTLIN
04. What is the Companion Object code block?
A companion object is used to define members that are tied to the class rather than to instances of the class, similar to static members in Java.

Example:

class MyClass {
    companion object {
        fun create() = MyClass()
    }
}

val instance = MyClass.create()
05. What is the Elvis operator?
The Elvis operator (?:) is used to provide a default value if the left-hand expression is null.

Example:

val length: Int = name?.length ?: 0
06. What is a nullable type?
In Kotlin, you can declare a variable that can hold a null value by appending a ? to its type.

Example:

val name: String? = null
07. What is Coroutine?
Coroutines are Kotlin's way of handling asynchronous programming. They allow execution of long-running tasks without blocking the main thread, ensuring smooth UI interactions.

Example:

GlobalScope.launch {
    delay(1000L)
    println("Coroutine!")
}
08. Difference between async and launch in Coroutine?
launch: Launches a coroutine that doesn’t return a result.
async: Launches a coroutine that returns a Deferred object, which holds a result.

Example:

val result = GlobalScope.async {
    delay(1000L)
    "Hello"
}.await()

GlobalScope.launch {
    println("World")
}
09. Example for filter function usage
The filter function is used to filter elements from a collection based on a predicate.

Example:

val numbers = listOf(1, 2, 3, 4, 5)
val evenNumbers = numbers.filter { it % 2 == 0 }
println(evenNumbers)  // Output: [2, 4]
10. What is an Open class?
In Kotlin, classes are final by default. To allow a class to be inherited, you must declare it as open.

Example:

open class Parent
class Child : Parent()
11. What is a Data Class?
A data class in Kotlin is a class primarily used to hold data. It automatically provides equals(), hashCode(), toString(), and copy() methods.

Example:

data class User(val name: String, val age: Int)
12. How to use Lambda function?
A lambda function is a function literal, which can be passed as an argument or stored in a variable.

Example:

val sum: (Int, Int) -> Int = { a, b -> a + b }
println(sum(2, 3))  // Output: 5
13. What is a Suspend function?
A suspend function is a special type of function that can be paused and resumed. It's used in coroutines for long-running tasks.

Example:

suspend fun fetchData() {
    delay(1000L)
    println("Data fetched")
}
14. Available scopes of Coroutine?
GlobalScope: A coroutine scope that spans the entire application's lifecycle.
CoroutineScope: Allows the creation of a custom scope tied to lifecycle components.
viewModelScope: Used with ViewModel in Android.
lifecycleScope: Tied to the lifecycle of an Android component.

Example:

lifecycleScope.launch {
    // Coroutine within lifecycle scope
}
15. What is a Sealed class?
A sealed class is a restricted class hierarchy where all possible subclasses are known at compile time. This makes it useful for handling restricted options like in a state machine.

Example:

sealed class Shape
class Circle : Shape()
class Rectangle : Shape()
16. How to handle exception in Coroutine?
You can handle exceptions in coroutines using try-catch or by using a CoroutineExceptionHandler.

Example:

val exceptionHandler = CoroutineExceptionHandler { _, exception ->
    println("Caught $exception")
}

GlobalScope.launch(exceptionHandler) {
    try {
        throw Exception("Error")
    } catch (e: Exception) {
        println("Caught in catch: ${e.message}")
    }
}
MVVM
01. What is two-way data binding?
Two-way data binding allows changes in the UI to automatically update the underlying data, and vice versa. It ensures that if the data changes, the UI reflects the change, and if the user interacts with the UI (e.g., input in a text field), the underlying data model gets updated.

Example:

<EditText
    android:id="@+id/editText"
    android:text="@={viewModel.userName}" />
In the above, any change in userName in the ViewModel will reflect in the EditText, and any user input in the EditText will update userName in the ViewModel.

02. What is the ViewModel?
The ViewModel is a component in the MVVM architecture that holds and manages UI-related data. It survives configuration changes (like screen rotations) and interacts with the Model to get data for the View. It ensures the separation of UI logic from business logic.

Example:

class MyViewModel : ViewModel() {
    val userName = MutableLiveData<String>()
}
03. Difference between MVVM and MVP?
The MVVM (Model-View-ViewModel) and MVP (Model-View-Presenter) architectures are both popular design patterns for structuring Android applications, but they have key differences in how they separate concerns and handle communication between components.

1. Structure and Responsibilities:
MVVM (Model-View-ViewModel):
MVP (Model-View-Presenter):

2. Communication Flow:
MVVM:The View binds to properties in the ViewModel using data-binding or observing LiveData.The ViewModel communicates with the Model to retrieve or update data but doesn't directly update the View. Instead, the View observes the ViewModel for changes.
MVP:The Presenter communicates with both the View and the Model. The Presenter takes user input from the View and updates the View with changes in the Model. This direct communication between the Presenter and View can lead to tighter coupling.

3. Coupling and Testability:
MVVM:
MVP:

4. Use of Data Binding:
MVVM:
MVP:

04. How to use MVVM?
To implement MVVM:

Model: Define your data source or repository.
ViewModel: Create ViewModel classes to hold and manage UI data.
View: Use XML layouts and data binding to connect UI elements to ViewModel properties.

Example:

Model: Data class or repository fetching from an API or database.
ViewModel: LiveData holds data.
View: XML with data binding or observing LiveData.

Jetpack
01. What is the Navigation Component?
The Navigation Component in Jetpack is a framework for navigating between fragments or activities, providing a consistent and declarative way to manage app navigation and handle deep links.

Example: Using a navigation graph:

<fragment
    android:id="@+id/firstFragment"
    android:name="com.example.FirstFragment"
    tools:layout="@layout/fragment_first" />
02. What is the Room database?
Room is an abstraction over SQLite in Android that provides an easy way to create, manage, and query databases. It offers compile-time checking of SQL queries and integrates with LiveData and coroutines.

Example:

@Entity
data class User(@PrimaryKey val id: Int, val name: String)

@Dao
interface UserDao {
    @Query("SELECT * FROM user")
    fun getAllUsers(): LiveData<List<User>>
}

@Database(entities = [User::class], version = 1)
abstract class AppDatabase : RoomDatabase() {
    abstract fun userDao(): UserDao
}
03. What are the Jetpack components?
Jetpack components are a suite of libraries to help in app development, such as:

Architecture: ViewModel, LiveData, Room, Data Binding, WorkManager.
UI: Navigation, MotionLayout, RecyclerView.
Behavior: CameraX, Notification, Permissions.
Foundation: AppCompat, Android KTX, etc.

04. What is View Binding?
View Binding is a feature that generates binding classes for XML layouts, enabling type-safe interactions with UI elements. It replaces findViewById().

Example:

val binding = ActivityMainBinding.inflate(layoutInflater)
setContentView(binding.root)
binding.textView.text = "Hello, View Binding!"
Design
01. What is the difference between guideline and barrier in ConstraintLayout?
Guideline: A static, invisible line used to align views. Can be horizontal or vertical.
Barrier: A dynamic constraint that adjusts based on the size of other views. It pushes other views and adjusts according to the content size.

Example:

Use a guideline for aligning views to a specific point.
Use a barrier when the position depends on the size of another view.

02. What is the ems property of TextView?
The ems property defines the width of a TextView in terms of the width of a capital "M" in the current text size. It essentially sets a fixed width for the text element.

Example:

<TextView
    android:ems="10"
    android:text="Hello" />
03. What is chainStyle in ConstraintLayout?
chainStyle defines the behavior of views that are part of a chain in ConstraintLayout. There are three styles:

spread: Views are evenly distributed.
spread_inside: First and last views are attached to the parent, and the rest are distributed evenly.
packed: Views are packed together.

Example:

app:layout_constraintHorizontal_chainStyle="packed"
04. Can we use Material Components in layouts with AppCompat themes?
Yes, Material Components can be used with AppCompat themes, but it's recommended to use Material themes (Theme.MaterialComponents.*) for full compatibility.

05. What is Motion Layout?
MotionLayout is a subclass of ConstraintLayout that provides animation and transition capabilities. It allows you to define complex animations and layout transitions in XML.

Example:

<MotionScene>
    <Transition>
        <KeyFrameSet>
            <KeyPosition ... />
        </KeyFrameSet>
    </Transition>
</MotionScene>
#Playstore
01. Difference between Alpha testing, Beta testing, Internal testing?
Alpha Testing: Initial testing phase with limited internal users for identifying critical bugs.
Beta Testing: Testing with a wider audience outside the organization to gather feedback before final release.
Internal Testing: For a small group of testers within the organization for early testing.

02. What is App Signing?
App Signing is the process of securing your app using a cryptographic key to ensure its authenticity and prevent unauthorized modifications.

03. Which information is included in Google Play Store listing?
App name, description, icon, screenshots, version details, category, content rating, privacy policy, and more.

04. What is Keystore file?
A Keystore file is a secure container that holds certificates and private keys used for signing Android apps.

05. How to set up In-App Purchase in Playstore?
Integrate the Google Play Billing Library into your app.
Configure products in the Google Play Console.
Implement purchase flow in the app to handle transactions.

#Firebase
01. What is FCM? How to Implement FCM?
FCM (Firebase Cloud Messaging): A service that allows you to send notifications and messages to Android, iOS, and web apps.
Implementation: Add Firebase to your project, configure notifications, and send messages using Firebase Console or server API.

02. What is Remote Config?
Firebase Remote Config allows you to update your app's behavior and appearance by changing server-side parameters without releasing a new version.

03. Which types of database are provided by Firebase?
Firebase Realtime Database: A NoSQL cloud database for real-time data syncing.
Cloud Firestore: A scalable, flexible NoSQL database for structured data storage.

04. Usage of Firebase Analytics?
Firebase Analytics tracks user behavior in your app, such as events, user demographics, and in-app purchases, helping you improve user experience.

05. What is Dynamic Link? How can we use it?
Dynamic Links are smart URLs that work across different platforms. They direct users to specific content inside your app and can survive installation.

#Google Map
01. What is Geo-fencing?
Geo-fencing creates a virtual boundary around a geographic area, triggering specific actions (e.g., sending notifications) when the user enters or exits.

02. Which permissions are required to show current location on Map or to access the location?
ACCESS_FINE_LOCATION: For precise GPS-based location.
ACCESS_COARSE_LOCATION: For approximate location using network data.

#Scenarios
Describe a scenario where onPause() and onStop() would not be invoked.
When the activity is abruptly terminated by the system (e.g., due to low memory) or by killing the app process directly, onPause() and onStop() may not be called before onDestroy().

#VCS
01. CI/CD
Continuous Integration/Continuous Deployment: A process of automating code integration, testing, and deployment in software development.

02. Commit
Saving code changes to a local repository with a message describing the updates.

03. Push
Uploading committed changes from a local repository to a remote repository.

04. Clone
Copying a repository from a remote server to your local machine.

05. Merge
Combining changes from different branches into a single branch.

06. Rebase
Reapplying commits on top of another base branch, often used to maintain a clean project history.

#Project Management Tools
01. Have you used any project management tools?
Yes, tools like Jira, Trello, and Asana help manage tasks, track project progress, and collaborate with teams.

#Testing
01. What is Unit Testing?
Testing individual units or components of code in isolation to ensure they work as expected.

02. What is Integration Testing?
Testing the integration of different units to ensure they work together correctly.

03. What is Espresso Testing?
Espresso is an Android testing framework for writing UI tests to simulate user interactions within an app.

04. What is UI Automator?
UI Automator is a testing framework for interacting with and automating UI across apps and the Android system.
