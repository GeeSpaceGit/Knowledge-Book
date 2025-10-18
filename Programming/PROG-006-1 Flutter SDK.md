# What Need in Development?
1. A computer 
   Can develop Flutter apps on Windows, macOS, Linux or ChromeOS. However, Xcode only runs on  macOS, making a Mac necessary to build and deploy apps for iOS.
2. The Flutter SDK
3. An editor, such as Android Studio or Visual Studio Code.
4. One device
   Can run in an iOS  simulator or Android emulator, but running Flutter apps on a physical device will give you the true user experience.
5. Developer account
   To deploy to the Apple App store or Google Play Store, will need a valid account on each.

# Step to Setting up
1. Download the SDK. https://flutter.dev/
>[!note] 
>Flutter organizes its SDK around channels, which are different development branches. 
>- Beta Channel
>  New features or platform support will be available first to certain features like platforms or native SDK support.
>- Stable Channel
>  Has been vetted and tested and has less chance of breaking.

2. To check have set it up correctly, run the following command in a terminal
```bash
flutter help
```

![[Pasted image 20251017222340.png]]
These subcommands are a gateway to the tools that come with Flutter. Will see project management tools, package management tools, package management tools and tools to run and test apps.

3. Flutter Doctor, which guides you through installing all the missing tools.
![[Pasted image 20251017222712.png]]

4. Setting up an IDE
   Flutter team officially supports 3 editor: Android Studio, Visual Studio Code and Emacs.
5. Trying it out
   2 recommended ways to create a new project:
	   - IDE^[Android Studio, Visual Code Studio]
	   - Flutter command-line
   
6.  The template project runs on adb
![[Pasted image 20251017233429.png]]
   