---
done: true
---
![[Pasted image 20251017211736.png]]
# What is this?
- A software development toolkit from Google for building cross-platform apps.
- Consist of a series of package, plugins and widgets.
- Easier way to get an app up and running on any one platform, let alone multiple. Can be more productive than thought possible.
![[Pasted image 20251016084919.png]]

>[!note] Flutter is not a language
>- It uses Dart as its programming language. It's an object-oriented C-style language.
>- Can compile to native code, which makes it fast. It also uses a virtual machine (VM) with a special feature: hot reload. This lets update code and see the changes live without redeploying it.
>- Programmers have been promised the ability write once and run anywhere.

# How it performance?
- Can build a high-quality app that's performant and looks great, very quickly. Truly does work well with both desktop and web.
- Other cross-platform toolkits have tried to abstract the underlying OS by adding a layer on top of the native UI layer. This leaves the developer with the lowest common set of features available.
- Skia - Flutter's widgets exist parallel to native widget due to its custom user interface rendering engine.  That means that the toolkit controls how the UI looks and behaves, which allows for consistent behaviour between platform.
# Who's Flutter for
- For both new or experienced developer who want to start an app with minimal overhead. 
- For someone looking to make an app that runs on multiple devices, either right away or in the future.
- For someone who prefer to build declarative UIs with the support of a large, open-source community.
- For developers with experience on one platform who want to develop an app that works across many. 

>[!note] The popular apps from some of the world biggest companies are built with Flutter.
>- BMW
>- eBay
>- Google Pay
>- Tencent
>- Toyota

![[Pasted image 20251016090356.png]]

# What is the strength of this?
1.  Compare with other SDK
	- Flutter is open-source. That means its evolution and know what's coming and even try out new featured in development. Can also create own patches and packages or contribute code. And can be involved in the community to help others or contribute to its future direction.
	- Flutter is purposely attractive, using Google's Material Design out of the box. It's also easy to apply Cupertino widgets to get an iOS-like appearance. The UI is fully customizable, allowing to make an app that looks right.
	- Flutter was designed with accessibility in mind, with out-of-the-box support for dynamic font sizes and screen readers and a ton of best practices around language, contrast and interaction method.


2. Developer Side
	- Uses the Dart programming language. It is modern, modern, UI-focused language that compiled to native ARM or x86 code or cross-compiled to JavaScript. It supports all the great language features people have come to like and expect, such as async/ await for concurrency management and type inference for clean, type-safe code.
	- Flutter comes with great animations and transitions, and can build custom widgets as well. Because widgets are composable, can be creative and flexible with the UI. For example, can put video behind a scroll view or put a toolbar on top of a canvas.
	- Flutter supports C and C++ interoperability as well as platform channels for connecting to Kotlin and Java on Android and Swift or Objective-c on iOS.

3. Reload and Eestart
	- Hot reload allows you to make updates to the code and the UI that rebuild the widget tree, then deliver them live to emulators and devices without to reload state or recompile your app.
	- Hot restart takes a reset the state, but still faster than a full restart.
	- Full restart which recompiles and redeploys. Use it when make certain significant changes to the code, including anything changing state management.

# What is the limitation of this?
1. Games and Audio
	- For complex 2D and 3D games, you'd probably prefer to base your app on a cross-platform game engine technology like Unity or Unreal. They have more domain-specific features like physics, sprite and asset management, game state management , multiplayer support and so on.
	- It doesn't have sophisticated audio engine yet, so audio editing or mixing apps are at a disadvantage over those that are purpose-built for a specific platform.

2. Apps With Specific Native SDK Needs
	- It supports many, but not all, native features. Fortunately, you can usually create bridges to platform-specific node. However, if the app is highly integrated with a device's features and platform SDKs, it might be worth writing the app using the platform-specific tools. It also produces app binaries that are the bigger in size than those built with platform frameworks..
	- It might not be a practical choice if you are only interested in a single platform app and have deep knowledge of that platform's tools and language. For example, if working with a highly-customized iOS app based on CloudKit that uses all the native hardware, MLKit, StoreKit, extensions, maintaining and talking advantage of those features will be easier using SwiftUI. Of course, the same goes for a heavily-biased Android app using Jetpack Compose.

3. Certain Platforms
	- It doesn't support every platform. Platforms like watchOS, tvOS and certain iOS app extension have specific needs it doesn't yet support.

# What is the History of it
- Flutter team chose the Dart language, which Google also developed, for its productivity enhancements. Its object-oriented type system and support for reactive and asynchronous programming give it clear advantages over JavaScript. Most importantly, Google built the Dart VM into the Chrome browser, allowing web apps written in Dart to run at native speeds.
- Skia is another Google-based open source project that powers the graphics on Android, Chrome browsers, Chrome OS and Firefox. It runs directly on the GPS using Vulkan on Android and Metal on iOS, making the graphics layer fast on mobile devices. Its API allows Flutter widgets to render quickly and consistently, regardless of the host.
- Flutter is migrating to a new rendering engine called Impeller that brings better performance and consistency. It provides the same benefits as Skia and improves upon them. Impeller is the default rendering engine for all iOS apps developed with Flutter 3.10 and above.
# The Flutter Architecture
- It has a modular, layered architecture. This allows to write application logic once and have consistent behaviour across platforms, even though the underlying engine code differs depending on the platform. The layered architecture also exposes different points for customization and overriding as necessary.
![[Pasted image 20251017205441.png]]

## Flutter Framework and Plugins
- It is written in Dart and contains the high-level libraries that you'll use directly to build apps. This includes the UI theme, widgets, layout and animations, gestures and foundational building blocks.
- High-level features like JSON serialization, geolocation, camera access, in-app payments. This plugin-based architecture lets you include only the features app needs.

## Engine
- Contains the core C++ libraries that make up the primitives that support Flutter apps. The engine implements the low-level primitives of the Flutter API, such as I/O, graphics, text layout, accessibility, the plugin architecture and Dart runtime. 
- It also responsible for rasterizing Flutter scenes for fast rendering onscreen.

## Embedder
- It is different for each target platform and handles packaging the code as a stand-alone app or embedded module.

# Several sublayers on framework layer
![[Pasted image 20251017210459.png]]

- UI Theme
  Which uses either the Material (Android) or Cupertino (iOS) design language. This affects how the controls appear, allowing to make app look just like a native one.
- Widget layer
  Where will spend the bulk of UI programming time. This is where compose design and interactive elements to make up the app.
- Rendering layer^[Beneath the widgets layer]
  Which is the abstraction for building a layer.
- Foundation Layer
  Provides basic building blocks, like animations and gestures, that build up the higher layers.