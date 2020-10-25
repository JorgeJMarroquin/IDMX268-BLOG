---
template: blog-post
title: Now you See me Now you Don't
slug: /NowyouSeemeNowyouDont
date: 2020-10-24 13:42
description: Introducing to a new level of designing. Tricks and twists to play
  around CSS transitions and Animations and advices to have an interactive
  website without loosing consistency and attention from the user.
featuredImage: /assets/fredrick-tendong-hvyepjyehdq-unsplash.jpg
---
<!--StartFragment-->

If what you want is to give life to your web page projects, if what you want is to step up with the next level of designing, if what you want is to transform your next projects, as well as your legacy websites, to the latest in designs and trends. So what you really need are CSS <i>transition</i> and CSS <i>transform</i> properties. 

These two tools together can take your website to become fresh and user friendly. In this blog, we will dig into the use of these two properties from a basic perspective. To make it simple and easy, I will show you the basics of them for the immediate  implementation on your current projects. As the saying goes, "practice makes a master". 

<h2>Let's start with <i>transform</i></h2>

The <i>transform</i> property is the ability to transform an element from one state to another, for example, a yellow rectangle, can be <i>transform</i> it into a red rectangle. Likewise, we could rotate that rectangle, or make it change from one position to another.

<h2>CSS Syntax example using “scale” transform</h2>

Let’s take a look of the <i>transform</i> scaling property in an element, the syntax would be as follows:

<!--EndFragment-->

![tranform: scale](/assets/imagea1.jpg "<h2>scale</h2>")

Therefore, the following code will create the following results:

```
/*Haml*/

.square


/*SCSS*/

.square {
  background: darkturquoise;
  border-radius: 5px;
  height: 100px;
  margin: 100px;
  width: 100px;
  
  &:hover {
    transform: scale(2);
  }
}
```

![Scale 1](/assets/squarebefore.jpg "Square before scaling it to 2.")

![Scale 2](/assets/squareafter.jpg "Square after scaling it to 2")

By scaling to 2, the element will get increased as twice as much as its original size. You can do the same just with de X-axis to increase the width, or the y-axis to increase the height, for example, <i>transform: scaleY(2)</i>

In the previous example we are using the "transform" property inside a "&:hover" selector so when the pointer hovers over the image, the change will immediately take place. However, transform properties can also be used in other div. blocks to change the shape of an element.

<h2>CSS transitions</h2>

Now its time to take a look to the cherry on the top of the whipped cream. Using the <i>transform</i> property without a proper <i>transition</i> property, would make your design looks  unexpected and even abrupted. As we revisit the previous example, we should realized that the abrupted change that took place when we hover over the element makes it harder for viewer to enjoy.

Here is where a <i>transition</i> comes along.  By applying a proper transition, we can resize our "dark turquoise square" example smoothly and gradually. 

The two properties that are required to make this transition functional are, <i>transition-property</i> and <i>transition-duration</i>.  The <i>transition-property</i> will help us to specify the CSS property where we want the transition to take place. And the <i>transition-duration</i> will specify the timing of that transition (in seconds or milliseconds).

Alternatively, you can use a full shorthand sequence to declare these attributes. Moreover, you can add duration, timing, and even delay in the same code line as follows:

![Transition Shorthand](/assets/transitionshorthand.jpg "Transition Shorthand")

Now let's add a transition to our "dark turquoise square" example.

```
/*Haml*/
.square


/*SCSS*/
.square {
  background: darkturquoise;
  border-radius: 5px;
  height: 100px;
  margin: 100px;
  transition: transform 1s;
  width: 100px;
  
  &:hover {
    transform: scale(2);
  }
}
```

In our example we added in line 11 a <i>transition</i> to the <i>transform</i> property and we add "1s" for time. 

<https://codepen.io/jorgejmarroquin/pen/BazpMNW>

![Transform Scale Example with a Transition](/assets/squarewithtransition.jpg)

Using these two properties will help you to have a interactive website, but just keep in mind that while it is important to have an interactive and fresh design on your projects, it is also imperative to keep consistency and simplicity to have a well design website. As I mentioned in previous articles, if you over-design a website, you might run into the risk of loosing the real meaning and purpose of it, deploying the wrong message to your viewers.

<h2>skew</h2>

With <i>skew</i> property, elements tilts on one direction or the other. As with the <i>scale</i> property, the <i>skew</i> property can use X and Y axes to have specific behaviors.

![transform: skew](/assets/skew1.jpg "<h2>CSS Syntax examples for <i>skew</i></h2>")

![transform: skew](/assets/skew.jpg)

Following our dark turquoise square example, lets apply this variant to see who it behaves.

```
/*HTML*/
<div class="square"></div>

/*SCSS*/
.square {
  background: Khaki;
  border-radius: 5px;
  height: 150px;
  margin: 100px;
  transition: transform 1s;
  width: 150px;
  
  &:hover {
    transform: skew(-50deg, 40deg);
  }
}
```

This will result in our square to move in its own ratio by -50 degrees for the X axe, and 40 degrees for the Y axe as follows:

<https://codepen.io/jorgejmarroquin/pen/pobRYpo>

![An example of <i>transform: skew</i>](/assets/finalskew.jpg)

<h2><i>transform-origin</i></h2>

The <i>transform-origin</i> property helps you to specify the location origin of the transform, meaning that you can't put this property together with the transform property. In the case of our example, <i>transform-origin</i> can not be in the hover block. For example, if we want to rotate our dark turquoise square not from the center of its ratio, but instead from any other point of the element, use percentages such as 0% 100% or 100% 0%. Also, you can accomplish this behavior by specifying the rotation of the element by typing <i>left top</i> or  <i>left bottom</i> or <i>right top</i> or <i>right bottom</i>.

The syntax would be as follows:

![Example using <i>transform-origin<i/>](/assets/origin.jpg)

If we add this to our dark turquoise square example it will be as follows:

```
/*HTML*/
<div class="square"></div>


/*CSS*/
.square {
  background: skyblue;
  border-radius: 5px;
  height: 150px;
  margin: 100px auto;
  transform-origin: right bottom;
  transition: transform 1s;
  width: 150px;

  &:hover {
    transform: rotate(500deg);
  }
}
```

Adding <i>transform-origin: right bottom</i> to our dark turquoise square example would take the square from the right and turn it to the left as well as from the top to the bottom in a 500 degrees.

<https://codepen.io/jorgejmarroquin/pen/pobRYBg>

![transform-origin](/assets/transform-origin.jpg)

And to clarify, transitions in general, don't have to be necessarily in a <i>:hover</i> block. Here an simple example of a transition called from the parent block:

```
/*HTML*/
<div class="box"></div>


/*CSS*/
.box {
  width: 150px;
  height: 150px;
  background: red;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  -webkit-transition: background-color 2s ease-out;
  -moz-transition: background-color 2s ease-out;
  -o-transition: background-color 2s ease-out;
  transition: background-color 2s ease-out;
}

.box:hover {
  background-color: green;
  cursor: pointer;
}


```

<https://codepen.io/jorgejmarroquin/pen/GRqWRPw>

![TransitionFromParentBlock](/assets/parentblock.jpg)

If you specify a delay, you have to specify the duration of it first.

<h2>Unsupported Properties</h2>

Some properties cannot be transitioned due to the lack of animatable behavior. I would recommend to you to visit <https://www.w3.org/TR/css-transitions-1/#animatable-properties>  for a comprehensive list of properties that currently are not animatable supported properties.

<h2>What is Next</h2>

With all these elements been transformed, shifted, rotated, slanted, stretched etc etc, you should be wandering what's next. Well, 3D graphics is the next thing, however, 3D has been around for a few years now. With programs such as Flash, Canvas, or WebGL, 3D environments have been part of the community for quiet a while now. But thanks to the CSS transformations, now front-end developers can enhance their designs by adding a new dimension to a traditional website.

To finalized this article, I would highly recommend you, ones again, to keep consistency on your transitions and animations. While it is good to have interactive websites, it is also important not to make them distracted to the users. Stick to the core four properties (Scale, Position, Rotation, Opacity), get the timing right, think about accessibility and use variables to keep things consistent are some tips to keep in your website projects smooth and user friendly.