---

layout:     default
title:      Ghost Buttons Tutorial: Much Button, So Ghost
type:     post
navigation:   false

date:       2014-12-17
excerpt:   I'll show you how to create some cool ghost button styles for your website's CTA.
categories:   Tuts
gradient:     3
image:      exposure.jpg
details:    false

author:     Jason Beaton
bio:      I'm a freelance web architect who enjoys solving problems, and making things look good.
twitter:    "http://twitter.com/thnkco"
facebook:     "http://facebook.com/yetle99"
google:     "http://google.com/+jasonbeaton"
linkedin:     "www.linkedin.com/pub/jason-beaton/2b/920/942/"
pinterest:    "http://pinterest.com/yetle99"
dribbble:     "http://dribbble.com/parkerrr"

---

# Ghost buttons: Much Button, Such Ghost
With the rise of full-image backgrounds on websites, the ghost button style has become a go-to element design to create a unique call to action button that allows the background image to be seen through the button. 

Click the link for some examples: [Ghost Button Examples]

### So in this write-up, I'll show you how to create some basic ghost button styles you can apply to your site.

I'll assume that you've got a site built out with some links on it. Preferably a call-to-action link somewhere on your page that you'd like to apply this style to. I would suggest using this button styling sparingly. No need to go all [Bob Ross] on this technique. 

I'll go over 3 basic styles:

* A basic Style
* A hovered-color transition
* A size transition effect

We'll start with assigning a class to your link element. Let's call this "ghost-button". It should look something like this:
  
  <a class="ghost-button" href="#">Clicky Click</a>

Let's look at the CSS of the basic ghost button. 
### Basic ghost button

    .ghost-button { 
  display: inline-block; 
  width: 200px; 
  padding: 8px;
  color: #fff;
  border: 1px solid #fff;
  text-align: center;
  outline: none;
  text-decoration: none;
  }
  .ghost-button:hover,
  .ghost-button:active {
  background-color: #fff;
  color: #000;
  }

Here, we're simply adding a background color and changing the color of the text to black so it will show on the (now) white background. on hover and active states. Pretty simple, right? Alright, let's turn it up a bit.

### On hover-color transition ghost button

  .ghost-button {
  display: inline-block;
  width: 200px;
  padding: 8px;
  color: #fff;
  background-color: transparent;
  border: 2px solid #fff;
  text-align: center;
  outline: none;
  text-decoration: none;
  -webkit-transition: all .3s ease-in-out;
  -moz-transition: all .3s ease-in-out;
  -ms-transition: all .3s ease-in-out;
  -o-transition: all .3s ease-in-out;
  transition: all .3s ease-in-out;
  }

  .ghost-button:hover,
  .ghost-button:active {
  background-color: #2a85c3;
  border-color: #3fbc9f;
  color: #fff;

This applies the transition property to gradually change the background color, border color, and text color to whatever you set the values to in the hover and active states. It's really smooth and it works on all modern browsers (including IE 10 and up).

This last example is my favorite. it uses the same transition effect, but on the width of the element. It's a really neat way to animate a button and put emphasis on the CTA. 

### Size transition ghost button

  .ghost-button {
  display: inline-block;
  width: 200px;
  line-height: 25px;
  padding: 8px;
  color: #fff;
  border: 2px solid #fff;
  text-align: center;
  outline: none;
  text-decoration: none;
  -webkit-transition: all .3s ease-in-out;
  -moz-transition: all .3s ease-in-out;
  -ms-transition: all .3s ease-in-out;
  -o-transition: all .3s ease-in-out;
  transition: all .3s ease-in-out;
  }

  ghost-button:hover,
  ghost-button:active {
  width: 220px;
  }

There are a few things you should look out for on this transition effect. One is the height. Since the transition-property is set to "all", you can optionally set the hover and active states to include a height change (or anything else you want to transition). You can conditionally set this to just width by changing the transition-property to: 
  
  transition: width .3s ease-in-out;

> You can add any properties to the hover and active states that you want to transition, but only if you've set them in the parent element.  

So we've explored some different ghost button styles and took advantage of the transition property. You can really go wild with this, but in the essence of minimalism, don't. CTA's are there to affirm your decision, not to be a distraction. Leave a comment with a link to your implementation of the ghost button, as I'd love to see what you come up with. Happy coding everyone! 





[Bob Ross]: https://www.youtube.com/watch?v=MghiBW3r65M
[Ghost Button Examples]: http://websiteswithghostbuttons.tumblr.com/