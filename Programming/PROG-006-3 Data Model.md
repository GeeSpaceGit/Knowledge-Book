# Create a Class
- Also need to supply some data for the app to display. Did load this data either data either from a local database or a JSON database or a JSON-based API.
- This is a hard-coded list of recipes. Includes a list of names and images
 
```dart
class Recipe{
	String label;
	String imageURL;
	
	Recipe(
		this.label,
		this.imageUrl,
	);
	
	static List<Recipe> samples = [
		Recipe(
			'Spagetthi',
			'assets/Spagetthi.jpg',
		),
		
		Recipe(
			'Tomato Soup',
			'assets/Tomato_Soup.jpg',
		),
		
		Recipe(
		'Grilled Chesse',
		'assets/Grilled_Cheese.jpg',
		),

	];
}
```

## Add images
1. Open pubspec.yaml in the project root folder.
2. Lines specify that ***assets/*** is an the assets folder and must be included with the app. ![[Pasted image 20251018221455.png]]
>[!info] Notification of modifying ***pubspec.yaml***
>![[Pasted image 20251018221800.png]]
>- IDE show a notification to get dependencies for project.
>- This happens because it works as app's manifest. When change it, also need to let Dart's VM that it changed and it needs to update all the bundled code.


