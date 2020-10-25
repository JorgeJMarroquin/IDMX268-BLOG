---
template: blog-post
title: Now you See me Now you Don't
slug: /NowyouSeemeNowyouDont
date: 2020-10-24 13:42
description: Introducing to a new level of designing. Tricks and twists to play
  around CSS transitions and Animations and advices to have an interactive
  website without loosing consistency and attention from the user
featuredImage: /assets/fredrick-tendong-hvyepjyehdq-unsplash.jpg
---
<!--StartFragment-->

If what you want is to give life to your web page projects, if what you want is to step up to the next level of designing and modernims, if what you want is to transform your pages, including legacy web, that you have created in the last fashion cry. So what you need are CSS transitions and CSS transforms. These two together can take your page to be dynamic and easy to use. Just keep in mind to keep your projects simple, subtle and consistent. The idea of using this CSS pair is to streamline your projects without making your user lose attention or get distracted. To make it simple and easy, I will show you basic ideas of its use and easy implementation. As they say over there, practice makes perfect. When after having read and studied this article, you will surely be ready for more extensive uses of these two attributes. Let's start with "transform". Transforms is the ability to transform an element from one state to another, for example, a yellow rectangle, we can transform it into a red rectangle. Likewise, we could rotate that rectangle, or make it change position, from right to left.

<h2>CSS Syntax example using “scale” transform</h2>

Let’s take the example of scaling an element, the syntax would be as follows:

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

By scaling to 2 the element will get increased by twice as much as its original size. You can do the same just with de X-axis to increase the width, or the y-axis to increase the height, for example, <i>transform: scaleY(2)</i>

In the previous example we are using the "transform" property inside a "&:hover" selector so when the pointer hovers over the image, the change will immediately take place. However, transform properties can also be used in other div. blocks to change the shape of an element.

<h2>CSS transitions</h2>

Now its time to take a look to the cherry on the top of the whipped cream. Using the <i>transform</i> property without a proper <i>transition</i> property, can make your designs look  unexpected and even abrupt. As we revisit the previous example of the square, although the scaling of our square looks interesting, we should realized that the abrupted change from one size to the other make it hard for viewer to enjoy.

Here is where a <i>transition</i> comes along.  By applying a proper transition, we can make our square to make its change smoothly and gradually. 

But before that, we have to two properties that are required to make a transition to be functional, these are <i>transition-property</i> and <i>transition-duration</i>.  The <i>transition-property</i> will help us to specify the CSS property where we want the transition to take place. And the <i>transition-duration</i> will specify the timing of that transition (in seconds or milliseconds).

Alternatively, you can use a full shorthand sequence to declare these attributes. Moreover, you can add duration, timing, and even delay in the same code line as follows:

![Transition Shorthand](/assets/transitionshorthand.jpg "Transition Shorthand")

Now let's add a transition to our dark turquoise example.

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

In our example we add in line 11 a <i>transition</i> to the <i>transform</i> property and we add "1s" for time. 

<https://codepen.io/jorgejmarroquin/pen/BazpMNW>

![Transform Scale Example with a Transition](/assets/squarewithtransition.jpg)

Using these two properties will help you to have a interactive website, but just keep in mind that while it is important to have an interactive and fresh design on your projects, it is also imperative to keep consistency and simplicity to have a well design website. As I mentioned in previous articles, if you over-design a website you run to the risk of loosing the real meaning and purpose of it, deploying the wrong message to your viewers.

<h2>skew</h2>

With <i>skew</i> property, elements tilts on one direction or the other. As with the <i>scale</i> the <i>skew</i> property can use X and Y axes to have specific behaviors.

![transform: skew](/assets/skew1.jpg "<h2>CSS Syntax examples for <i>skew</i></h2>")

![transform: skew](/assets/skew.jpg)

Following our dark turquoise square example, lets apply this variant to it to see who it behaves.

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

This will result in our square to move in its own ratio by -50 degrees in the X axe, and 40 degrees in the Y axe as follows:

<https://codepen.io/jorgejmarroquin/pen/pobRYpo>

![An example of <i>transform: skew</i>](/assets/finalskew.jpg)

<h2><i>transform-origin</i></h2>

The <i>transform-origin</i> property helps you specify the location origin of the transform, meaning that you can't put this property together with the transform property. In the case of our example, <i>transform-origin</i> can not be in the hover block. For example, if we want to rotate our dark turquoise square not from the center of its ratio, but instead from any other point of the element, use percentages such as 0% 100% or 100% 0% you can accomplish this. Alternately you can specify the rotation of the element by writing <i>left top<i/> or  <i>left bottom<i/> or <i>right top<i/> or <i>right bottom<i/>.

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

Adding <i>transform-origin: right bottom</i> to our dark turquoise square would take the square from the right and turn it to the left and from the top to the bottom in a 500 degrees.

<https://codepen.io/jorgejmarroquin/pen/pobRYBg>

![transform-origin](/assets/transform-origin.jpg)

And to clarify, transitions doesn't have to be necessarily in a <i>:hover<i/> block. Here an simple example of a transition called from the parent block: