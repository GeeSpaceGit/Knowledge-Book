![[Pasted image 20251022172953.png]]

# ListView
- It's linear scrollable widget that arranges its children linearly and supports horizontal and vertical scrolling.
  ![[Pasted image 20251022174129.png]]
4 constructor:
1. ***children***
   That will construct every single in the list. Should us this of have a small number of children.
2. ***ListView.builder()***
   Takes in an ***IndexedWidgetBuilder*** and builds the list demand. It will only construct the children that are visible onscreen. Should use this if need to display a large or infinite number of items.
3. ***ListView.separated()***
   Takes 2 ***IndexedWidgetBuilders: itemBuilder*** and ***separatorBuilder***. Useful if want to place a separator widget between item.
4. ***ListView.custom()***
   gives more fine-grain control over child items.

# Setting Up the Explore Screen
![[Pasted image 20251022175410.png]]
- ***RestaurantSection***
  A horizontal scroll view that lets pan through different restaurants.
- ***CategorySection***
  A horizontal scroll view that pans through different categories.
- ***PostSection***
  A vertical scroll view that shows what friends up.
## Step to build
1. ***lib*** folder, create a new directory called ***screens***.
   ![[Pasted image 20251022175902.png]]
2. Create a new file called ***explore_page.dart***.
```dart title:'explore_page.dart'
import 'package:flutter/material.dart';
import '../api/mock_yummy_service.dart';

class ExplorePage extends StatelessWidget{
	// 1
	final mockService = MockYummyService();
	ExplorePage({super.key});
	
	// 2
	@override
	Widget build(BuildContext context){
		return const Center(
			child:Text(
				'Explore Page Setup'
				style: TextStyle(fontSize: 32.0),
				),
		);
	}
}
```

| Section | Description                                          |
| ------- | ---------------------------------------------------- |
| 1       | Create a ***MockYummyService*** - to mock responses. |
| 2       | Display a placeholder text.                          |
# Building Restaurant Section
![[Pasted image 20251022182849.png]]
1.  Building the restaurant section
```dart title:'libs/components/restaurant_section.dart'
import 'package:flutter/material.dart';

// 1
import '../components/restaurant_landscape_card.dart';
import '../models/restaurant.dart';

class RestaurantSection extends StatelessWidget{
	
	// 2
	final List<Restaurant> restaurants;
	
	const RestaurantSection({
		super.key,
		required this.restaurants,
	});
	
	@override
	Widget build(BuildContext context){
		
		// 3
		return Padding(
			padding: const EdgeInsets.all(8.0),
			
			// 4
			child: Column(
				crossAxisAlignment: CrossAxisAlignment.start,
				children:[
					const Padding(
						padding: EdgeInsects.only(
						left: 16.0,
						bottom: 8.0,
						),
						
						// 5
						child: Text(
							'Food near me',
							style: TextStyle(
								fontSize: 24,
								fontWeight: FontWeight.bold,
							),
						),
					),
					
					// 6
					Container(
						height:400,
						color: Colors.grey,
					),
				],
			),
		);
	}
}
```

| Section | Description                                                                          |
| ------- | ------------------------------------------------------------------------------------ |
| 1       | Import restaurant card component and model.                                          |
| 2       | ***RestaurantSection*** - ***StatelessWidget*** that requires a list of restaurants. |
| 3       | ***build()*** - start by applying some padding.                                      |
| 4       | Add a ***Column*** to place widgets in a vertical layout.                            |
| 5       | ***Text*** - This is the header for the "Food near me" section.                      |
| 6       | ***Container*** - 400 pixels tall and set the background color to ***grey***.        |
2. Import relevant .dart file.
```dart title:'explore_page.dart'
import '../components/restaurant_section.dart';
```
3. Return the ***RestaurantSection***.
```dart title:'explore_page.dart'
return RestaurantSection(restaurants: restaurnats);
```

![[Pasted image 20251022202056.png]]

4.  Implement the ***ListView***.
```dart title:'restaurant_section.dart'
// 1
SizedBox(
	height: 23,
	
	// 2
	child: ListView.builder(
		
		// 3
		scrollDirection: Axis.horizontal,
		
		// 4
		itemCount: restaurants.length,
		
		// 5
		itemBuilder: (context, index){
			
			// 6
			return SizedBox(
				width: 300,
				
				// 7
				child: RestaurantLandscapeCard(
					restaurant: restaurants [index],
				),
			);
		},
	),
),
```

| Section | Description                                                                                                               |
| ------- | ------------------------------------------------------------------------------------------------------------------------- |
| 1       | ***ListView*** - have a fixed a fixed height of 230 pixels. It acts as a container to constraint the height of the child. |
| 2       | ***ListView.builder*** - dynamically creates a list of items based on the provided data.                                  |
| 3       | Configure the items in the ***ListView*** to scroll horizontally.                                                         |
| 4       | Set the ***itemCount*** to be the length of restaurants list. Determine how many times the list should render.            |
| 5       | ***itemBuilder*** - return a widget for a given index of the list. It's invoked for each item in the restaurant list.     |
| 6       | Set a fixed width of ***300*** pixels for every restaurant card.                                                          |
| 7       | Create a ***RestaurantLandscapeCard*** and pass in the restaurant object based on the current index.                      |
5. Import relevant .dart file.
```dart
import 'restaurant_landscape_card.dart';
```

![[Pasted image 20251022203758.png]]

# Nested List Views
## Column Approach
![[Pasted image 20251022203932.png]]
### The Pros and Cons using this views

| Pros                                                                                                         | Cons                                                                                |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| ***RestaurantSection*** and ***CategorySection*** are oj because the scroll direction is horizontal.  ****** | ***PostSection*** scrolls in the vertical direction, but it only small scroll area. |
- This approach has a bad user experience because the content area is too small. The ***Cards*** already take up most of the screen.

## Nested ListView Approach
- Show 1 big rectangle boundary. ***ExplorePage*** holds the parent ***ListView***. There are only 3 children ***ListViews***, can use the default constructor, which returns an explicit list of children
![[Pasted image 20251022204356.png]]
### The benefit of this approach
1. The scroll area is a lot bigger, using 70 - 80% of the screen.
2. Can view more of friends' posts.
3. Can continue to scroll ***RestaurantSection*** or ***CategorySection*** in the horizontal direction.
4. When scroll upward. Flutter listens to the scroll event of the parent ***ListView***.

``` dart title:'explore_page.dart'
// 1
return ListView(
	
	// 2
	shrinkWrap: true,
	
	// 3
	scrollDirection: Axis.vertical,
	
	// 4
	children: [
		RestaurantSection(restaurants: restaurants),
		Container(
			height: 300,
			color: Colors.green,
		),
		Container(
			height: 300,
			color: Colors.orangem
		),
	],
);
```

| Section | Description                                                               |
| ------- | ------------------------------------------------------------------------- |
| 1       | Initialize a scrollable list of widgets.                                  |
| 2       | ***shrinkWrap*** sizes the ***ListView*** based on its children's height. |
| 3       | The list scrolls vertically.                                              |
| 4       | The list contains 3 child list view widget.                               |
- Can still scroll the ***Cards*** horizontally. When scroll up and down, will notice the notice the entire area scrolls! 
![[Pasted image 20251022205929.png]]

# Building Category Section
```dart title:'lib/components/category_section.dart'
import 'package:flutter/matrial.dart';
import '../models/food_category.dart';
import 'category_card.dart';

class CategorySection extends StatelessWidget{
	final List List<FoodCategory> categories;
	const CategorySection({
		super.key,
		required this.categories
	});
	
	@override
	Widget build(BuildContext context){
		return Padding(
			padding: const EdgeInsets.all (8.0),
			
			child: Column(
				crossAxisAlignment: CrossAxisAlignment.start,
				chilren:[
					const Padding(
						padding: EdgeInsets.only(
							left: 16.0,
							bottom: 8.0
						),
						child: Text(
							'Categories',
							style: TextStyle(
								fontSize: 24,
								fontWeight: FontWeight.bold,
							),
						),
					),
					
					SizedBox(
					
					)
				]
			)
		)
	}
}
```