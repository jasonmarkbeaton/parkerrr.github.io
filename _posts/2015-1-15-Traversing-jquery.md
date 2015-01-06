---

layout:     default
title:      Traversing JQuery
type:     post
navigation:   false

date:       2015-1-6
excerpt:    A short-ish post on what traversing in JQuery does, and why you should use it.
categories:   Tuts
gradient:     4
image:      DeathtoStock_Medium6.jpg
details:    false

author:     Jason Beaton
bio:      I'm a freelance web architect and marketer who enjoys solving problems, and making things look good.
twitter:    "http://twitter.com/thnkco"
facebook:     "http://facebook.com/yetle99"
google:     "http://google.com/+jasonbeaton"
linkedin:     "www.linkedin.com/pub/jason-beaton/2b/920/942/"
pinterest:    "http://pinterest.com/yetle99"
dribbble:     "http://dribbble.com/parkerrr"

---

## Traversing JQuery
There are some really great ways to speed up your JQuery, like:

+ Always descend from an #id
+ Chaining your methods
+ Traversing the DOM
+ And many more

I'd like to focus on traversing, since it's one of those magical features of JQuery that can be hard for beginners to comprehend.

## What's it all about? 
When first learning JQuery, the concept of traversing can be confusing. It's more typing, but it works faster. Why?

First, check out this [speed test]
You'll see that the clear winner (by speed) is the traversal. 

Now, the explanation in the simplest terms I can provide. Let's setup some code to use as a reference.

    <div id="cheese">
      <h1>These are our many types of cheese.</h1>
      <ul id="kindOfCheese">
        <li>Asiago</li>
        <li>Swiss</li>
        <li>Cheddar</li>
        <li>Colby</li>
        <li>Feta</li>
      </ul>
    </div>

So we have a list of cheeses, wrapped in an unordered list with an id of "kindofCheese", in a div with an id of "cheese". With some basic knowledge of JQuery you may have learned that if you want to select the last cheese in that list, you would use the following code...

    $(document).ready(function() {
      $("#cheese li:last")
    });

Sure, that will grab the last list element, but refactoring your code using traversal can make this query run faster.

    $(document).ready(function() {
      $("#cheese").find("li").last()
    });

That **.find** method helps us traverse the DOM. It's similar to our first approach, as in it gets us the result we're looking for, but it's slightly faster because of a few reasons. 

1.  JQuery is a library built *on top* of javascript. Javascript runs natively in your browser, whereas JQuery has to process it's own javascript code before handing it to the browser. JQuery uses a selector library called [sizzle]. All you really need to understand here is that it's not native to the DOM, so it's slower.
2.  Here's where it gets tricky. When you use more than one element in a JQuery selector, it HAS to use Sizzle to process. On the flip-side, if you use single elements in your selector, JQuery utilizes native DOM methods _(like getElementsByClassName, and getElementsByTagName)_ so you can take advantage of the native DOM speed benefits. 

## Short and Sweet
 So when you're building out your mega-giant-monolith application keep in mind that refactoring your javascript can save you a significant amount of speed by traversing the DOM natively. Likewise, you can just stop using JQuery, and go full-metal-jacket style into javascript so that you're only using native DOM methods. 

I hope this short article helps those who are beginning to learn JQuery to get a solid understanding of what things to look out for, so you can get started on the right foot and have an idea of where to start refactoring your code. 



[speed test]: http://jsperf.com/find-select-speed-test/3
[sizzle]: http://sizzlejs.com/