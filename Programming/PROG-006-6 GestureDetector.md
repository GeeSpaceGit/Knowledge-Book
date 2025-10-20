# GestureDetector
```dart
// 1
GestureDetector(
	
	// 2
	ontap:(){
		
		//3
		Navigator.push(
			context,
			MaterialPageRoute(
				builder:(context){
					// 4
					return Text('Detail page');
				},
			),
		);
	}
	
	// 5
	child: buildRecipeCard(Recipe.samples[index]),
	)
```


| Section | Description                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | Detects gesture widget.                                                                                                                        |
| 2       | ***onTap():*** the callback called when the widget is tapped.                                                                                  |
| 3       | ***Navigation*** - which manages a stack of pages.<br><br>***push()*** with a ***MaterialPageRoute*** will push a new Material page onto stack |
| 4       | ***builder*** creates the destination page widget.                                                                                             |
| 5       | ***GestureDectector***'s - defines the area where the gesture is active.                                                                       |
Tap a recipe and will see a black ***Detail page***.
![[Pasted image 20251018233536.png]]

# Creating an Actual target Page
- This creates a new ***StatefulWidget*** which has an initializer that takes the ***Recipe*** details to display.
>[!tip] RecipeDetail is a page.

```dart title:'recipe_detail.dart'
class RecipeDetail extends StatefulWidget{
	final Recipe recipe;
	
	const RecipeDetail({
		Key? key,
		required this.recipe,
	}) : super(key:key);
	
	@override
	State<RecipeDetail> createState(){
		return _RecipeDetailState();
	}
}
```

- need  \_RecipeDetailState to build the widget
>[!tip] \_RecipeDetailState is the content inside the page.

```dart title:'recipe_detail.dart' 
class _RecipeDetailState extends State<RecipeDetail>{

	Widget build(BuildContext context){
	
		// 1
		return Scaffold(
			appbar: AppBar(
				title: Text(widget.recipe.label),
			),
			
			// 2
			body: SafeArea(
				
				// 3
				child: Column(
					children:<Widget>[
						
						// 4
						SizedBox(
							height: 300,
							width: double.infinity,
							children: Image(
								image: AssetImage(widget.recipe.imageUrl),
							),
						),
						
						// 5
						const SizedBox(
							height: 4,
						),
						
						// 6
						Text(
						widget.recipe.label,
						style: const TextStyle(fontSize: 18),
						),
						
						// 7
						Expanded(
							
							// 8
							child: ListView.builder(
								padding: const EdgeInsets.all(7.0),
								itemCount: widget.recipe.ingredients.length,
								itemBuilder: (BuildContext context, int index){
									final ingredient = widget.recipe.ingredients[index];
									
									// 9
									return Text(
										'${ingredient.quantity} ${ingredient.measure} ${ingredient.name}'
									);
								},
							),
						),
					],
				),
			),
		);
	}
}
```

| Section | Description                                                                                                                                                                                                                           |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | ***Scaffold*** - the page's general structure.                                                                                                                                                                                        |
| 2       | ***SafeArea*** - a ***Column*** with some ***SizedBox*** and ***Text*** children.                                                                                                                                                     |
| 3       | ***SafeArea*** keeps the app from getting too close to the operating system interfaces, such as the notch or the interactive area of most iPhone                                                                                      |
| 4       | ***SizedBox*** around the ***Image*** - defines resizable bound for the image. <br><br>***height: 300*** is fixed but ***width*** will adjust to fit the aspect ratio.<br><br>Unit of measurement in Flutter is ***logical pixels***. |
| 5       | Spacer ***SizedBox***                                                                                                                                                                                                                 |
| 6       | ***TextStyle*** - has a ***style*** that's a little different than the main Card                                                                                                                                                      |
| 7       | ***Expanded*** - expands to fill the space in a ***Column***. The ingredient list will take up the space not filled by the other widgets.                                                                                             |
| 8       | ***ListView*** - one per ingredient                                                                                                                                                                                                   |
| 9       | ***Text*** - uses ***String interpolation*** to populate a string with runtimes values. You use the ***${expression}*** syntax inside the string literal to denote these                                                              |


| Step | Interface                            |
| ---- | ------------------------------------ |
| 1-6  | ![[Pasted image 20251019120028.png]] |
| 7-9  | ![[Pasted image 20251019123105.png]] |

