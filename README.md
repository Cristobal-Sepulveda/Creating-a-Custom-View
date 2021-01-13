Creating a Custom View Project

In this proyect i will make diferent custom Views

FIRST COMMIT: STARTED
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

SECOND COMMIT:
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
In this task, i will create an ImageView as a temporary placeholder for the
custom view.
Then I'll extend view to create the custom view & initialize the custom View
with drawing and paiting values.
//TODO 1.1
in the values folder i create a dimens resource with diferents dimmensions,
theses are just basic margins and the size of the fan control button
//TODO 1.2
Then, in strings.xml i add resources that i will need in the future
//TODO 1.3
Next, in activity_main.xml i add some properties to the TextView. this
textView acts as a label in the activity for the custom view
//TODO 1.4
Then, I add an ImageView. this will be a placeholder for the custom view that
I will create later
//TODO 1.5
After that, I create a new Kotlin class file called DialView. This class
extend View. The JVMOverloads annotation instrucs the Kotlin compiler to generate
overloads for this function that substitute default parameter values.
//TODO 1.6
at the top of the class, i add a enum class to represent the avaible fan speeds
& bellow this class i add some constants. theses are part of drawing the dial
indicators and labels
//TODO 1.7
Next, inside the DialView class, i define a few variables that i'll need to draw
the custon view. the variable:
1) PointF is a point with floating point coordinates.the radius is the current
 radius of the circle. this value is set when the view
is run on the screen
2) The FanSpeed is the current speed of the fan
3) finally point possession is an x-y point that will be used for drawing several of the Views
elements on the screen
These values are created and initialized here instead of when the view is actually
drawn to ensure that the actual drawing step runs as fast as possible.
//TODO 1.8
Also inside the DialView class definition I initialize a Paint object with a
handful of basic styles. As with the variables these styles are initialized here
to help speed up the drawing step.
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

THIRD COMMIT:
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
In this task, I will draw the fan controller custom view onto the screen; the dial
itself, the current position indicator, and the indicator labels with the unsized
changed and onDraw Methods.
I will also create a helper method, computecy for speed to calculate the current
xy position of the indicator label on the dial
I will start by overriding the onSizeChanged() method: this method is called
anytime the view size changes, including the first time it's drawn when the
layout is inflated.
override this method to calculate positions, dimensions, and any other values
related to your custom view size instead of calculating them every time you draw.
In this case, you use onSizeChanged() to calculate the current radius of the
dial circle element.
//TODO 2.1
in the DialView class bellow the initializations, override the unsized changed
method from the view class to calculate the size for the customer style.
input Kotlyn.math.min when requested.
// TODO 2.2
bellow onSizeChanged, add some code to define a compute xy for speed extension
function for the PointF class, inside import kotlin.method.cos & sin for cosine
and sine when requested.
this extension function on a PointF class calculates the xy coordinates on the
screen for the text label and current indicator 1, 2, 3 or 0, given the current
fan speed position and radius of the dial
this will be used in onDraw
//TODO 2.3
Override the onDraw method to render the view on the screen with a canvas and
paint classes.
1)inside onDraw, we're going to add a line of code to set the paint color to gray
or green, depending on wheter the fan speed is off or any other value and we
need to import Android.graphics.color
2)next we add code to draw a circle for to dial with a draw circle method.
this method uses the current view width and height to find the center of the circle,
the radius of the circle, and the current paint color. the width and height properties
are members of the view super-class and indicate the current dimensions after view.
3) next, we add code to draw a smaller circle for the fan speed indicator mark,
also with a draw circle method
--------------------------------------------------------------------------------
this part uses the PointF.computeXYForSpeed extension method to calculate the xy
coordinates for the indicators center based undercurrent fan speed.
4)Finally, we draw a fan speed labels 0,1,2 & 3 at the appropiate positions around
the dial. This part of the method calls PointF.computeXYForSpeed again to get the
position for each label and reuses the point position object each time to avoid
allocations. Then reuse draw text to draw the labels.
//TODO 2.4
To add a custom View to an app UI, you specified as an element in a XML layout.
control its appearance and behavior with XMl element attributes as you would for any
other UI element
So, reeplace the ImageView by root.DialView

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
