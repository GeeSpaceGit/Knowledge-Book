- It contains mock service class.
  ![[Pasted image 20251022173306.png]]
- ***MockYummyService*** is a service class that mocks a server response. It has ***async*** functions that wait to load mock data defined in each model class, ***FoodCategory***, ***Post*** and ***Restaurant***.
# API calls
- getExploreData():
  Return ExploreData. Internally, it makes a batch request and return 3 lists:
	- Restaurant
	- Food categories
	- Friend posts