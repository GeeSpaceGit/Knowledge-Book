# What is a Widget
- Widget is a building block for user interface. Using widgets is like combing Lego. 
- Flutter's declarative nature makes it super easy to build a UI with widgets. A widget is a blueprint for displaying the state of the app.

![[Pasted image 20251020162513.png]]

# Unboxing CategoryCard
![[Pasted image 20251020163029.png]]

| Widget           | Description                                                                    |
| ---------------- | ------------------------------------------------------------------------------ |
| ***Card***       | A material design container that wraps the content.                            |
| ***Column***     | Organizes content vertically with that wraps the content.                      |
| ***Stack***      | Overlays multiple widgets, used here to layer the image with 2 pieces of text. |
| ***ClipRRect***  | Provides rounded corners for the image.                                        |
| ***Image***      | Loads the image.                                                               |
| ***Text***       | Displays text from category details and static labels.                         |
| ***Positioned*** | Positions "Yummy" and "Smoothies" texts over the image.                        |
| ***RotatedBox*** | Rotates the text by 90°.                                                       |
| ***ListTile***   | Displays the category's name and number of associated restaurants.             |
# Widget Trees
- contains a build() method. In this method, create a UI composition by nesting widgets. This forms a tree-like data structure.
- Children - Each widget can contain other widgets.
- Provide a blueprint that describes how want to lay out UI. The framework traverse the nodes in the tree and calls each build() method to compose entire UI.

![[Pasted image 20251020165301.png]]
# Rendering Widgets
## Framework layer
![[Pasted image 20251020165500.png]]

| Layer                  | Description                                                                                                                   |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Material and Cupertino | UI control libraries built on top of the widget layer. They makes your look and feel like Android and iOS apps, respectively. |
| Widgets                | A composition abstraction on Widgets. It contains all the primitive classes needed to create UI controls.                     |
| Rendering              | A layout abstraction that draws and handles the widget's layout.                                                              |
| Foundation             | Contains core libraries that handle animation, painting and gestures.                                                         |
# 3 Trees
![[Pasted image 20251020170032.png]]

| Tree         | Description                                                                                                                      |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| Widget       | The public API or blueprint for framework. Developers usually just deal with this layer.                                         |
| Element      | Manages a widget and widget's render object. For every widget instance in the tree, there is a corresponding element.            |
| RenderObject | Responsible for drawing and laying out a specific widget instance. Also handles user interactions, like hit testing and gesture. |
# Types of Elements
- ComponentElement
  Composed of other elements. This corresponds to composing widgets inside other widgets.
- RenderObjectElement
  A type of element that holds a render object.
## Example for CategoryCard
![[Pasted image 20251020170608.png]]
- Flutter starts to build app by calling ***runApp()*** Every widget's ***build()*** method then composes subtree of widget. It creates a corresponding element for each widget in the widget tree.
- Element tree manages each widget instance and associates a render object to tell the framework how to render a particular widget.
