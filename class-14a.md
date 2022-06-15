# CLASS-14a

## CSS TRANSFORMS

The `transform` property in CSS3 offers new techniques to position and alter elements. It can be two-dimensional and three-dimensional. Each with their own individual properties and values.

* **2D Transforms:** Works on the `x` and `y` axes.

  * **Rotate:** Rotates an element from 0 to 360 degrees.
  * **Scale:** Changes the appeared size of an element.
  * **Translate:** Similar to relative positioning. Pushes and pulls an element in different directions without interrupting the normal flow of the document.
  * **Skew:** DistortS elements on the horizontal axis, vertical axis, or both.

* **3D Transforms:** Work on both the `x` and `y` axes, as well as the `z` axis. Help define length, width and depth of an element.

  * **Perspective:** It is like vanishing point, similar to what we see in three-dimensional drawings. Can be set in two different ways. One way includes using the perspective value within the transform property on individual elements, and the other on the parent element residing over the child elements being transformed.
  * **Perspective Depth Value:** The length value will set the depth of the perspective.
  * **Perspective Origin:** Identifies the coordinates of the vanishing point of a transform.
  * **Rotate, Scale, Translate and Skew:** Similar than 2D but can change the the `z` axis.

***

## CSS TRANSITIONS & ANIMATIONS

CSS3 allows us to write behaviors for transitions and animations within HTML and CSS, without the use of JavaScript or Flash.

* **Transitions:** Alter the appearance and behavior of an element whenever a state change occurs. Like when it is hovered over, focused on, active, or targeted.

  * **Transitional Properties:** Only properties that have an identifiable halfway point can be transitioned. Colors, font sizes, and the alike may be transitioned.
  * **Transition Duration:** The duration in which a transition takes place.
  * **Transition Timing:** The speed in which a transition will move.
  * **Transition Delay:** Sets a delay for the transition to happen.

* **Animations:** Allow the appearance and behavior of an element to be altered in multiple keyframes. Transitions provide a change from one state to another, while animations can set multiple points of transition upon different keyframes.

  * **Animations Keyframes:** Sets multiple points at which an element should undergo a transition.
  * **Animation Name:** Keyframes need to be assigned to an element.
  * **Animation Duration, Timing Function, & Delay:** Similar to transitions. We can set all these properties for animations.
  * **Animation Iteration:** We can set an animation to repeat itself numerous times.
  * **Animation Direction:** We can declare the direction an animation completes.
  * **Animation Play State:** Allows an animation to be played or paused using the running and paused keyword values respectively.
  * **Animation Fill Mode:** Identifies how an element should be styled either before, after, or before and after an animation is run.

***

>8 simple transitions that will wow users

1. Fade in
2. Change color
3. Grow & Shrink
4. Rotate elements
5. Square to circle
6. 3D shadow
7. Swing
8. Inset border

***

### Things I want to know more about

* Learn how to properly use animations.

***

[-back](https://alexriverau.github.io/reading-notes/)
