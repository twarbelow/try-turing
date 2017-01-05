---
title: Some More jQuery
layout: post
date: 2000-01-06
permalink: more-jquery
program: front-end
---

## Bringing It Together: jQuery and CSS Transitions Together

Consider a situation where we have three boxes. When that particular box is clicked, we want to toggle a class. How do we know which box was clicked?

It turns out that when we add an event listener using jQuery, we get a special little variable called `this`. Lucky for us, `$(this)` is set to the box we clicked on.

We want each box to have a button inside of it. When the user clicks the button, it should rotate the entire box. (We're rotating the box with a CSS class called `.click` because we're super original.) Let's look at some code.

<p data-height="300" data-theme-id="23788" data-slug-hash="vKGYzo" data-default-tab="js,result" data-user="turing" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/team/turing/pen/vKGYzo/">Rotating Buttons</a> by Turing School of Software and Design (<a href="http://codepen.io/turing">@turing</a>) on <a href="http://codepen.io">CodePen</a>.</p>

This code _does not_ work the way we'd like. What we need to do is when the user clicks on a button. Go up and find the box that it lives in and add the class to _that_ element. We can try it like this:

<p data-height="300" data-theme-id="23788" data-slug-hash="YWqzJo" data-default-tab="js,result" data-user="turing" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/team/turing/pen/YWqzJo/">Rotating Boxes</a> by Turing School of Software and Design (<a href="http://codepen.io/turing">@turing</a>) on <a href="http://codepen.io">CodePen</a>.</p>

You can see all of ways we can move around the DOM tree in [jQuery documentation](https://api.jquery.com/category/traversing/tree-traversal/).

<div class="try-it">
<h2>Try It: jQuery and Animations</h2>

<p>Right now, all of your headings change background color. Can you modify your jQuery so that only the specific heading that was clicked gets a background color?</p>
</div>

## Checking Key Presses

jQuery allows us to check for certain keys being pressed. Paste this in your JavaScript box and try it out:

```js
$(document).keydown(function (e) {
  var key = e.which
  if(key == '72') {
  	alert('you pressed h!')
  }
});
```

'72' is the the keycode for the h key. On the third line, we're checking to see if Take a look at other keycodes <a href="https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes">here</a>. 

For now, don't worry too much about the intricacies of structure in this construct; just know that it is a format you can use to figure out which key was pressed. 

<div class="try-it">
<h2>Try It: Using Keycodes</h2>

<p>Modify the keycode number and alert message to respond to a user pressing the down arrow key. NOTE: This is different from the "page down" key.</p>
</div>

## Combining Key Presses and Movement

Look at your previous example. Replace your alert with the line below. What happens? 

```js
$('div').css({marginTop: '+=15px'});
```

What happens if you change it to '-=15px' instead of '+=15px'? 

Try replacing marginTop with marginLeft.

<div class="try-it">
<h2>Try It: Movement Based on Key Presses</h2>

<p>Modify your program so that the block can move in all four directions. You might want to do some Googling!</p>

<p>If you're super stuck, look at the starter block of code below.</p>
</div>

```js
if(key == "40") {
	
} else if(key == "38") {
	
} else if(key == "37") {
	
} else if(key == "39") {
	
}
```