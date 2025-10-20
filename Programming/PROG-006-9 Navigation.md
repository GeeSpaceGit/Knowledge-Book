- Applying the right navigation structure makes it easy for users to navigate the information in app.
# BottomNavigationBar
1. Track current tab
```dart title:'home.dart'
int tab = 0;

```

2. Define a list of tabs the user can navigate between it.
```dart title:'home.dart'
List<NavigationDestination> appBarDestination = const [
	NavigationDestination(
		icon: Icon(Icons.credit_card),
		label: 'Catergory',
		selectedIcon: Icon(Icons.credit_card),
	),
	NavigationDestination(
		icon: Icon(Icons.credit_card),
		label: 'Post',
		selectedIcon: Icon(Icons.credit_card),
	),
	NavigationDestination(
		icon: Icon(Icons.credit_card),
		label: 'Restaurant',
		selectedIcon: Icon(Icons.credit_card),
	),
]
```

3. Add bottom navigation bar
```dart title:'home.dart'
// 1
bottomNavigationBar: NavigationBar(
	
	// 2
	selectedIndex: tab,
	
	// 3
	onDestinationSelected: (index){
		setState((){
			tab = index;
		});
	},
	
	// 4
	destinations: appBarDestinations,
)
```


| Section | Description                                              |
| ------- | -------------------------------------------------------- |
| 1       | Assigns ***NavigationBar*** to ***bottomNavigationBar*** |
| 2       | Set the active ***tab*** using ***selectedIndex***       |
| 3       | Updates the active tab on user selection.                |
| 4       | Defines the lists of tabs with ***appBarDestinations***  |
![[Pasted image 20251020130505.png]]

# Navigating between Pages
1.  This contains a list of container with different colors. Will replace each one with a unique card soon.
```dart title:'home.dart'
final pages = [
	Container(color: Colord.red),
	Container(color: Colord.green),
	Container(color: Colord.blue),
]
```

2. Displays 1 widget from pages based on the tab index, preserving the state of all widgets in stack.
```dart title:'home.dart'
body: IndexedStack(
	index: tab,
	children: pages,
),
```

3. Restart the app.

![[Pasted image 20251020132100.png]]

