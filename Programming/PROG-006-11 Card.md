# Custom card
## Display
- Text
- Image
- Button
## Layout
- Container
- Padding
- Stack
- Column
- SizedBox
- Row

# CategoryCard
![[Pasted image 20251020132254.png]]

- ***Card***
  A material design container that holds content and action about a single subject.
- ***Column***
  Vertically arranges it widget children - ***Stack*** and ***ListTile***
- ***ListTile***
  A widget that contains title and subtitle text.

```dart title:'lib/components/category.dart'
import 'package:flutter/material.dart';
import '../models/food_category.dart';

class CategoryCard extends StatelessWidget{
	
	// 1
	final FoodCategory category;
	
	const CategorCard({
		super.key,
		required this.category
	});
	
	@override
	Widget build(BuildContext context){
		
		// 2
		return Container();
	}
}
```

| Section | Description                                                      |
| ------- | ---------------------------------------------------------------- |
| 1       | ***FoodCategory*** - which will use later to display data in UI. |
| 2       | Return an empty ***Container***.                                 |
# Replace with CategoryCard
1. Import relevant .dart file.
```dart title:'home.dart'
import 'components/category_card.dart';
import 'models/food_category.dart';
```
2. Replace it with card. 
```dart title:'home.dart'
// 1
Center(
	
	// 2
	child: ConstrainedBox(
		constraints: const BoxConstraints(maxWidth: 300),
		
		// 3
		child: categoryCard(category: categories[0]),
	),
),
```

| Section | Description                                                        |
| ------- | ------------------------------------------------------------------ |
| 1       | ***Center*** - ensures the card widget is centered on the screen.  |
| 2       | Applies a maximum width of 300 pixels to the card widget.          |
| 3       | ***CategoryCard*** - pass the first mock category to be displayed. |
3. Hot restart.
![[Pasted image 20251020135308.png]]

# Constructing widget
1. Get text theme
```dart title:'category_card.dart'
final textTheme = Theme.of(context)
	.textTheme
	.apply(displayColor: Theme.of(context).colorScheme.onSurface);
```

2. Card widget content
```dart title:'category_card.dart'
return Card(
	child: Column(
		mainAxisSize: MainAxisSize.min,
		children:[
		],
	),
);
```

2. Stack widget, allow to overlay widgets on top of each other.
```dart title:'category_card.dart'
Stack(
	children:[
		// 1
		ClipRRect(
			borderRadius: const BorderRadius.vertical(
				top: Radius.circular(8.0)
			),
			child: Image.asset(category.imageUrl),
		),
		
		// 2
		Positioned(
			left: 16.0,
			top: 16.0,
			child: Text(
				'Yummy',
				style: textTheme.headlineLarge,
			),
		),
		
		// 3
		Postioned(
			bottom: 16.0,
			right: 16.0,
			child: RotatedBox(
				quarterTurns: 1,
				child: Text(
					'Smoothies',
					style: textTheme.headlineLarge,
				),
			),
		),
	],
),
```

| Section | Description                                                              |
| ------- | ------------------------------------------------------------------------ |
| 1       | ***ClipRRect*** - which clips the image with rounded corners at the top. |
| 2       | Position the text "Yummy" on the top left.                               |
| 3       | Rotate the text "Smoothies" 90 degrees and place it at the bottom-right. |

3. Hot restart.
![[Pasted image 20251020142527.png]]

# Square Card Footer
```dart title:'category_card.dart'
ListTile(
	// 1
	title: Text(
		category.name,
		style: textTheme.titleSmall,
	),
	
	// 2
	subtitle: Text(
		'${category.numberOfRestaurants} places',
		style: textTheme.bodySmall,
	),
),
```

| Section | Description                                                   |
| ------- | ------------------------------------------------------------- |
| 1       | Display the category name with a smaller title style.         |
| 2       | Display the number of restaurants in a small body text style. |
![[Pasted image 20251020143229.png]]
# Post card
![[Pasted image 20251020143431.png]]
- Card
  Provides a material design card that can hold related pieces of information or content.

- Padding
  Adds a uniform padding of 16.0 pixels around the content inside it to provide some provide some spacing.
## Step
1. Set up the basic structure for the ***PostCard***.
```dart title:'lib/components/post_card.dart'
import 'package:flutter/material.dart';
import '../models/post.dart';

class PostCard extends StatelessWidget{
	final Post post;
	
	const PostCard({
		super.key,
		required this.post,
	});
	
	@override
	Widget build(BuildContext context){
		final textTheme = Theme.of(context)
			.textTheme
			.apply(
				displayColor: Theme.of(context).colorScheme.onSurface,
			);
		return Card(
			child:Padding(
				padding: const EdgeInsets.all(16.0),
				child: Row(
					crossAxisAlignment: CrossAxisAlignment.start,
					children:[
					],
				),
			),
		);
	}
}

```

2.  Import relevant .dart file into ***home.dart***.
```dart title:'home.dart'
import 'components/post_card.dart';
import 'models/post.dart';
```

3. Replace with ***Post Card***.
```dart title:'home.dart'
Center(
	child: Padding(
		padding: const EdgeInsets.all(16.0),
		child: PostCard(post: posts[0]),
	),
),
```

4. Hot reload.
![[Pasted image 20251020145222.png]]
# Child Widget
![[Pasted image 20251020145253.png]]
1. Add Circle Avatar used to display a profile image or user's avatar in a circular shape.
```dart title:'post_card.dart'
CircleAvatar(
	radius: 25,
	backgroundImage: AssetImage(post.profileImageUrl),
),
```

2.  Add 16-pixel padding between the 2 widgets.
```dart title:'post_card.dart'
const SizedBox(
	width: 16.0,
)
```

3. Add expanded widget
```dart
// 1
Expanded(
	child: Column(
		mainAxisSize:MainAxisSize.min,
		crossAxisAlignment: CrossAxisAlignment.start,
		children: [
			Text(
				post.comment,
				maxLines: 2,
				overflow: TextOverflow.ellipsis,
				style: textTheme.titleMedium
			),
			Text(
			'${post.timestamp} mins ago',
			style: textTheme.bodySmall,
			),
		],
	),
),
```

| Section | Discussion                                                                                                                                            |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | ***Expanded*** - makes the child occupy all available space.                                                                                          |
| 2       | ***MainAxisSize.min*** aligns them to occupy minimum space.<br>***CrossAxisAlignment.start*** horizontally aligns the child widgets to the left side. |
| 3       | Display 2 ***Text*** widgets, the post contents followed by post's timestamp.                                                                         |
![[Pasted image 20251020152859.png]]
# Landscape Card
![[Pasted image 20251020152939.png]]

Widgets compose ***RestaurantLandscapeCard***:
- ***Card***
  A material design card that contains related pieces of information.
- ***Column***
  Arranges its children widgets in vertical line.
- ***ClipRRect***
  Clips its child with a rounded rectangle border.
- ***AspectRatio***
  Constrains the child's aspect ratio.
- ***Image***
  Displays the restaurant's image, covering the available space
- ***ListTile***
  A widget that contains title and subtitle text.

1. Set up the basic structure for the ***RestaurantLandScapeCard***.
```dart title:'lib/components/restaurant_landscape_card.dart'
import 'package:flutter/material.dart';
import '../models/restaurant.dart';

class RestaurantLandscapeCard extends StatelessWidget{
	final Restaurant restaurant;
	
	const RestaurantLanscaprCard({
		super.key,
		required this.restaurant,
	});
	
	@override
	Widget build(BuildContext context){
		final textTheme = Theme.of(context)
		.textTheme
		.apply(
			displayColor: Theme.of(context)
			.colorScheme
			.onSurface
		);
		return Card(
			child: Column(
				mainAxisSize: MainAxisSize.min,
				children:[
				],
			),
		);
	},
} 
```

2. Import relevant .dart file in ***home.dart***.
```dart title:'home.dart'
import 'components/restaurant_landscape_card.dart';
import 'models/ restaurant.dart';
```

3. Replace with Restaurant Landscape.
```dart title:'home.dart'
// 1
Center(
	
	// 2
	child: ConstrainedBox(
		constraints BoxConstraints(maxWidth: 400),
		child: RestaurantLandscapeCard(
			
			// 3
			restaurant: restaurants[0],
		),
	),
),
```

| Section | Description                                                                                           |
| ------- | ----------------------------------------------------------------------------------------------------- |
| 1       | ***Center*** - widget ensures the card widget is centered on the screen.                              |
| 2       | Applies a maximum width of 400 pixels to the card widget.                                             |
| 3       | Set ***RestaurantLandscapeCard*** widget as the child - pass the first mock restaurant to be display. |
4. Hot restart.
![[Pasted image 20251020155407.png]]
# Landscape Card Child Widget
1. Add image and widget.
```dart title:'restaurant_landscape_card.dart'
ClipRRect()
	// 1
	borderRadius:
		const BorderRadius.vertical(
			top: Radius.circular(8.0),
		),
	
	// 2
	child: AspectRatio(
		aspectRatio: 2,
		child: Image.asset(
			restaurant.imageUrl,
			fit: BoxFit.cover
			),
	),
)
```

| Section | Description                                                                                                    |
| ------- | -------------------------------------------------------------------------------------------------------------- |
| 1       | ***borderRadius*** - rounds the top corners with an 8.0 unit radius.                                           |
| 2       | ***AspectRatio*** - displays an image with a 2:1 width-to-height ratio. The image scales to fit its container. |

2. Add ListTile
```dart
ListTile(
	
	// 1
	title:Text(
		restaurant.name, 
		style: textTheme.titleSmall,
	),
	
	// 2
	subtitle: Text(
		restaurant.attributes,
		maxLines: 1,
		style: textTheme.bodySmall,
	),
	
	// 3
	onTap: (){
		print('Tap on $(Tap on ${restaurant.name}');
	},
),
```

| Section | Description                                                                           |
| ------- | ------------------------------------------------------------------------------------- |
| 1       | ***title*** - Shows the restaurant's name with a specific style.                      |
| 2       | ***subtitle*** - Displays the restaurant's attributes, truncated if more than 1 line. |
| 3       | ***onTap*** - Prints the restaurant's name to the console when tapped.                |
3. Hot restart.
![[Pasted image 20251020160846.png]]
![[Pasted image 20251020161301.png]]