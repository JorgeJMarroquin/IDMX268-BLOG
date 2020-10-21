---
template: blog-post
title: The Good the Bad and the Ugly
slug: /good_bad_ugly
date: 2020-10-17 11:42
description: Among the objectives of this article are to learn to get around
  some limitations of old browser versions, maintain consistency between
  different browsers such as Chrome and Firefox among others as well as
  recognize that as developers we must maintain constant support to our
  applications. And that regarless of the screen sides and customer's devices,
  developers should develop to make their experiences seamlessly and smooth.
featuredImage: /assets/front-image.jpg
---
**<h2>How to Follow Changes and Additions to CSS:</h2>**

CSS is a language that is in constant updated and / or modification. Even when you think you are a master in the use of CSS, you come across more specs or new features that you didn't know existed. One easy way to get up to date in terms of accesbility and support is to visit The World Wide Web Consortium <https://www.w3.org/>. Here we can found specifications and the use of different CSS features currently supported.

I would like to share with you my personal guide and some usefull tips to help you to find CSS support in a broad of the most popular browsers. 

First, we have to understand that the web developer's job is to work around to deal with different types of browsers, versions and screen sides that millions of users around the world use. Although we might not be able to develop for every single one of them, at least we should to be able to develop for the most commonly use among those browsers and screen sides.

A tip to determine if your CSS works in your specific browser of preference is to use Queries. For example, if we convert a float item into a grid item, the float property will lose its performance and will push the items to the left, especially if we are using percentage in the float item.

![Image1](/assets/image1.jpg)

![Image2](/assets/image2.jpg "Using floats we can create a four column layout, widths and margins need to be set in %")

When displaying into a grid property the percent will apply but only to the width of the grid track, not to each item separately.

<!--EndFragment-->

![Image3](/assets/image3.jpg)

![Image4](/assets/image4.jpg)

A faster way to test this type of behaviors prior to deploying is name @supports. Most of the browsers has this tool built it in for which we can use to try different properties and values and the content inside that Query will responds if it does or doesn’t to support the feature. You can ask specifically if a feature is NOT supported by using @supports not.

```
@supports not (display: grid) {
    .item {
        /* CSS from browsers which do not support grid layout */
    }
}
```

You can also try multiple properties at the same time use “and” or if you need a to choose between one or another property use “or”.

<!--EndFragment-->

```
@supports (display: grid) and (shape-outside: circle()){
    .item {
        /* CSS from browsers which support grid and CSS shapes */
    }
}
```

```
@supports (display: grid) or (display: flex){
    .item {
        /* CSS from browsers which support grid or flexbox */
    }
}
```



Therefore, if you want to test a property and value for “display: grid” do as follows:

<!--EndFragment-->

```
.grid > .item {
    width: 23%;
    margin: 0 1%;
}

@supports(display: grid) {
    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        column-gap: 1%;
    }

    .grid > .item {
        width: auto;
        margin: 0;
    }
}
```

![Image 9](/assets/image9.jpg)

To get the result as shown above, type the following HTML and CSS code:

```
/*HTML*/
div class="grid">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  <div>Four</div>
</div>



/* CSS*/
* { box-sizing: border-box; }

body {
  margin: 40px;
  background-color: #fff;
  color: #444;
  font: 1.4em Arial, sans-serif;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-auto-rows: 100px;
  grid-gap: 20px;
}

.grid > * {
padding: 10px;
  border: 5px solid rgba(214,129,137,.5);
  border-radius: 5px;
  background-color: rgba(233,78,119,.5);
  color: #fff;
  float: left;  
  width: 23%;
  margin: 0 1%;
}

@supports (display:grid) {
  .grid > * {
    width: auto;
    margin: 0;
  }
}
```



All the previous does not really need to be inside a feature query. In this example, the things that must be inside the query are the margin and width properties. These properties are needed for old browsers.

**<h2>Browser Engines</h2>**

Although it is extremely difficult to have exactly the same design of a website in all browsers, there are always ways to maintain consistency between them in such a way that we can reach a wider target audience.

<!--EndFragment-->

![Browser engines](/assets/image10.jpg "Popular browsers and its engines.")



Although the developer tends to develop towards how works better in the Google chrome browser due to its popularity in the market share, we should not understimate or overlook support for any other browser.

![Market share](/assets/image11.jpg "Market Share")

Another way to figure out  CSS properties browser's support is by visiting <https://caniuse.com/> and checking the desire property and its fuctionaly.

An excellent practice a good developer should follow is what is call "Graceful degradations Vs Progressive Enhancement" which are responsive strategies that a developer can take when developing for different browsers and its different versions.

**<h2>Graceful degradation</h2>** 

Is when a website is built a design with the latest features modern browsers can handled, and from there gradually coding downwards to provide support for older browsers.

**<h2>Progressive enhancement</h2>**

Is when a website is built, at first, with a basic baseline version of the website, and gradually it builds up improve versions to support advanced functionality

<!--EndFragment-->

![Graceful Degradation Vs Progressive Enhancement](/assets/image12.jpg "Resposive Strategies")

**<h2>Fault Tolerance</h2>**

Fault tolerance is a feature build in CSS that allows you to embedded code in case a browser comes across a CSS line that it cannot interpret. The fault tolerance feature will then ignore that line and will read the embedded line instead for interpretation and therefore replacement of the original line that was previously ignore. Here and example to request HTTP for a modern browser and in the legacy IE 8.

![Image13](/assets/image13.jpg "Fault Torelance")

<!--StartFragment-->

As mentioned previously, [Can I Use](https://caniuse.com/) is a good tool to check support, it also can help to import relevant analytics data of any location to check for support from smaller browser’s support in other locations, such as in India or in the UK.

For example, CSS grid support in the UK shows as follows:

![CanIuse](/assets/image14.jpg "CSS grid support")

While this may seem irrelevant at first glance, it must be considered what type of user you want to reach. A company based in the US may want to expand its operations in emerging markets such as India, so it is imperative to ensure that all the features of the company website are read as fluently as possible in that destination country.

For example, up to Oct 2017, browsers in these emerging markets have not yet get support for grid. You probably have not even heard about some of the following browsers, and still they hold a decent amount of popularity in those countries.

![StatCounter Global Stats](/assets/image15.jpg "StatCounter Global Stats")

Up to that period, for example, **UC browser** had not get support for Grid Layout.

In conclusion, as a developer, you need to scope out the type of market and users you want to reach. You need to see the type of support you want to give to them. Take in consideration that you will always be required to visit your “end product” (webpage or application) and ensure that it will run as smoothly as possible on the user screen’s device of his choice as well as on its browser.

<!--EndFragment-->