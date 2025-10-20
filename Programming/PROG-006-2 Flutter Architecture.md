- Build a basic app from scratch, giving the chance to get the hang of the tools and the basic Flutter app structure.
- Customize the app and find out how to use a few popular widgets like ***ListView*** and ***Slider*** to update its UI in response to changes.
- Creating a simpler app will let you see just how quick and easy it is to build cross-platform apps with Flutter.

# Making the App Yours
- This defines a new Dart ***class*** named ***MyApp*** which ***extends*** or inherits from ***StatelessWidget***.
- StatelessWidget doesn't change after you build it. 

```dart title:'main.dart'
class MyApp extends StatelessWidget{
}
```
# Refactor
- Could change it manually in multiple places, will reduce the chance if a copy-and-paste error or typo by using the IDE's ***rename*** action instead

1.  Refactor > Rename menu item. 
2. Click on ***MyApp*** in class ***MyApp...*** and navigate to either refactor option.
3. In the popup, rename ***MyApp*** to ***RecipeApp*** and tap on the ***Refactor*** button.

```dart
void main(){
	runApp(const RecipesApp());
}

class RecipesApp extends StatelessWidget{
	const RecipesApp({super.key});
}
```

- ***main()*** is the entry point for the code when the app launches.
- ***runApp()*** tells Flutter which is top-level widget for the app.

>[!info] 
>Hot reload won't include the code change. Run the new code need to perform a hot restart.

# Styling App

| Before                               | After                                |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20251018204717.png]] | ![[Pasted image 20251018204707.png]] |
```dart title:'main.dart'
// 1
@override
Widget build(BuildContext context){ 
	
	// 2
	final ThemeData theme = ThemeData();
	
	// 3
	return MaterialApp( 
	
		// 4
		title: "Recipe Calculator",
		
		// 5
		theme: theme.copywith(
			colorScheme: ColorScheme.fromSeed(
				seedColor: Colors.greenAccent,
			),
		),
		// 6
		home: const MyHomePage(
			title: "Recipe Calculator"
		),
	);	
 }
```

| Section | Description                                                                                                                                                                                                                                                                     |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | **widget's build()*** - The entry point for composing together other widget to make a new widget.<br><br>***@override*** - tells the Dart analyser that this method is supposed to replace the default method from ***StatelessWidget***.<br>                                   |
| 2       | Theme determines visual aspect like aspects like color.<br><br>***ThemeData*** - show the standard Material defaults.                                                                                                                                                           |
| 3       | ***MaterialApp*** - uses Material Design.                                                                                                                                                                                                                                       |
| 4       | ***tittle:*** - that uses to identify the app. The UI won't display this.                                                                                                                                                                                                       |
| 5       | ***theme.copyWith:*** - By copying the theme and replacing the color scheme with a custom one are changing the app's color.<br><br>***fromseed*** constructor - generating shades and tones that ***ThemeData*** uses to style widgets following Material Design specification. |
| 6       | ***home:*** - This still uses the same ***MyHomePage*** widget as before, but now have updated the title and displayed it on the device.                                                                                                                                        |
# Clearing the App
```dart title:'main.dart'
class _MyHomePageState_ extends State<MyHomePage>{
	@override
	Widget build(BuildContext context){
		
		// 1
		return Scaffold(
			
			// 2
			appBar: AppBar(
				title: Text(widget.title),
			),
		
		// 3
			body: SafeArea(
			
				// 4
				child: Container(),
			),
		);
	}
}
```

| Section | Description                                                                                                                                                                        |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | ***Scaffold*** : provides the high-level structure for a screen. In this, using 2 properties.                                                                                      |
| 2       | ***AppBar*** : gets a title property by using a ***Text*** widget that has a ***title*** passed in from ***home : MyHomePage(title: ''Recipe Calculator')*** in the previous step. |
| 3       | ***body: SafeArea***, which keeps the app from getting too close the operating system interfaces such as the notch or interactives areas like Home                                 |
| 4       | ***SafeArea*** has ***child*** widget, which an empty ***Container*** widget                                                                                                       |

# Widget Tree
![[Pasted image 20251018224644.png]]

1. Android Studio Flutter 
  
2. Inspector View > Tool Windows > Flutter Inspector 
 ![[Pasted image 20251018224829.png]]
 This view shows all the widgets onscreen and how they are composed. As you scroll, you can refresh the tree.