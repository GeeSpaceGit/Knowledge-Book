# ListView.builder
```dart
// 1
child: ListView.builder(
	
	// 2
	itemCount: Recipe.samples.length,
	
	// 3
	itemBuilder: (BuildContext context, int index){
		
		// 4
		return Text(Recipe.samples[index].index);
	},
)
```


| Section | Description                                                                                                                     |
| ------- | ------------------------------------------------------------------------------------------------------------------------------- |
| 1       | Builds a list using ***ListView***.                                                                                             |
| 2       | ***itemCount*** - Determines the number of rows the list has. length is the number of objects in the ***Recipe.samples*** list. |
| 3       | ***itemBuilder*** - Builds the widget tree for each row.                                                                        |
| 4       | ***Text*** widget : Displays the name of the recipe                                                                             |
![[Pasted image 20251018222721.png]]