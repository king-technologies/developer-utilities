a) GlobalKey assigns a unique identifier for a widget to maintain its
state during the entire app session, whereas ValueKey is used to
uniquely identify a widget's position in its parent widget, ensuring its
state is preserved during widget rebuilds.
b) GlobaLKey is used to access the state of a widget across the widget
tree, while ValueKey is used to identify widgets in collections for the
framework.
c) GlobalKey is specifically designed for identifying form fields and
ensuring their data is collected accurately, while ValueKey is used
for optimizing animation performance by maintaining widget
identity.
d) GlobaLKey is used for triggering re-renders of widgets in response to
state changes, while ValueKey enables the customization of widget
properties based on user interactions.



In Dart, how can you implement the Visitor design
a) By using extension methods to add new visit operations to existing
classes without modifying them.
b) By defining an abstract accept method in the base class and
implementing it in derived classes to call the appropriate visit
method.
c) By declaring a single visit method in the base class that uses type
checks to perform different actions for each derived class.
d) By implementing a visit interface in each class that directly calls the
methods of other classes without an accept method.


* In Dart, how can you create a mixin that can only be applied to
classes that implement a specific interface?*
a) By using the on keyword followed by the interface name in the mixin
declaration.
b) By specifying the interface as a generic type parameter in the mixin
declaration.
c) By using the implements keyword instead of with when applying the
mixin to a class.
d) By explicitly checking the type in the mixin's constructor and
throwing an exception if it does not implement the required
interface.


In Flutter, what is the purpose of using keys in widgets?*
a) To increase the performance of rendering widgets by caching them.
b) To enable communication between widgets in different parts of the
widget tree.
c) To uniquely identify and control the state of widgets during the build
process.
d) To assign a global identifier that can be used for analytics and
debugging purposes.


What is the primary rote of the State class in a
StatefulWidget in Flutter?*
a) It defines the immutable properties of the widget.
b) It holds the current state and mutable properties of the widget.
c) It manages the build context and widget Lifecycle.
d) It defines the structure and layout of the widget tree.



Which of the following changes would allow the MyPainter
widget to repaint when a state change occurs?*
a) Change the shouldRepaint method to return true.
b) Wrap the CustomPaint widget in a StatefulWidget and call setState
when the state changes.
c) Modify the MyPainter class to extend StatelessWidget instead of
CustomPainter.
d) Change the paint method to call setState to trigger a repaint.



Which of the following statements is true regarding the use of
CustomPaint in Flutter?*
a) CustomPaint automatically handles repainting when the underlying
data changes without any additional code.
b) The CustomPainter provided to CustomPaint must always be a
stateless class to ensure it performs efficiently.
c) To trigger a repaint of a CustomPaint widget, you need to call the
markNeedsPaint method on the CustomPainter.
d) CustomPaint provides a canvas on which you can draw using a
CustomPainter, and you need to override the paint and
shouldRepaint methods in CustomPainter.


* Which of the following statements is true regarding the use of
Futures and Streams in Dart?*
a) A Future represents a sequence of asynchronous events that
produce multiple values over time, whereas a Stream represents a
single asynchronous computation that yields a single value or error.
b) The await keyword can be used with both Future and Stream objects
in an asynchronous function to pause execution until a value is
available.
c) The Stream.fromlterable constructor can be used to create a stream
from a collection of values that are emitted one by one.
d) The then method of a Future is used to transform the stream of
values it produces, whereas the map method of a Stream is used to
handle the result of the asynchronous computation.


Which of the following statements about using mixins in Dart
is true?
a) A class can only apply a single mixin at a time.
b) Mixins can be applied to both classes and other mixins.
c) The order in which mixins are applied to a class does not affect the
behavior of the resulting class.
d) Mixins cannot have constructors.


which of the following statements regarding routing in
(utter are true?*
a) The Navigator.pushReplacement method is used to push a new route
and remove all previous routes from the stack.
b) Using the onGenerateRoute callback allows for dynamic route
generation, but it cannot handle unknown routes that are not
predefined.
c) The ModalRoute.of(context) method can be used to retrieve the
arguments passed to the current route.
d) The Navigator.popUntil method can be used to push a new route
onto the stack until a specified route is reached.