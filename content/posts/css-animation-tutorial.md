---
title: "CSS Animation Tutorial"
date: 2022-11-29T16:02:35+01:00
draft: false
show_reading_time: true
---

# Why create SVG animations using CSS?

Animations created with JavaScript (or animated gifs) can become heavy and cause web pages to load slowly. SVGs are light and can be either referenced or embedded directly in the code. The clue to another advantage of using SVGs is in the name - Scalable Vector Graphics. They will look just as great on a tiny mobile screen as on a huge retina display.
Thanks to the animation features in CSS3 we can create simple (yet enticing!) animations that are easy on your page without the need to run a JavaScript.

> This animation introduction is suitable for everyone with basic HTML and CSS knowledge. 
> I will explain how to create a custom animation to create a cool effects.
> You'll need a vector editing program and a text editor. 
 
We'll create the animation directly in the browser, in an online code editor Codepen.

## In your vector-editing program

This animation works best on simple images. I have created mine in Adobe Illustrator but open source tools such as Inkscape will also do the trick. The most important thing is that you can save it as an SVG file.
Once you've created your image as an SVG, open it in a text editor (such as Notepad, SublimeText etc.) and then copy all into the clipboard.

## Create a pen in CodePen

Codepen is an online editor that allows you to create and share code snippets. I find it particularly useful for working with CSS animation as you can see the effects immediately, rather than having to constantly switch between the text editor and the browser as you would have to do when working locally. You don't even need to create an account, 
1. create a new 'pen' by clicking **start coding** in the top left-hand corner.
2. Paste the code you copied from your text editor into the HTML section. It should contain two sections - metadata, for example:
`xml version="1.0"`
and the main SVG section - make sure you have the closing SVG tag `</svg>`.

### Basic SVG shapes
SVGs are human-readable, some basic SVG elements included in my image are
  `<circle> <path> <line> `
To find out more about SVGs, check out this page.

## Head over to the CSS section

The first thing I want to do is to make sure that my image sits perfectly in the middle of the screen - I can reference the SVG directly through the CSS rule

```css
svg {
       position: absolute; 
       margin:auto;
     }

```

The next steps will explain how I animated individual parts of the image.
Animating the circle
I'll start with the outermost layer, the circle. There's only one element in this image so I can use this as a selector without adding the element id.

```css
svg circle {
           animation: circle-outline 10s alternate infinite;
           }

```

The `animation` shorthand property allows me to define the most important features described by properties such as:
- `animation-name`: I named mine circle-outline, you can choose whatever you want for your animation
- `animation-duration`: the default is 0, so you have to specify how long the animation should be running for. 
  My animation lasts 10 seconds - I wanted to achieve a soothing effect, rather than a flashy one with a shorter cycle. 
- `animation-direction`: specifies how the animation will be played: forwards, backwards or in alternate cycles. Mine runs in alternate cycles, so the stroke is going in one direction (forwards) then moves back on the loop
- `animation-iteration-count`: The infinite value specifies the number of times an animation should run. I want mine to run forever but you can also set the animation to just 1 or any other number.

##  Animating the opacity

Now that we have set the most important features of the animation, we can move to @keyframes rule which controls the animation (this is where the animation takes place):

```css 
    @keyframes circle-outline 
{ 
from {
opacity: 0;
          }
to 
         { 
opacity: 1;
          }

```

I have set the opacity to 0 in the first section so the shape is completely invisible, and to 1 which means it is fully visible (the values between 0-1 can be used or %). As the whole animation lasts 10 seconds, the image slowly appears on the screen, then slowly disappears as the animation is played back in alternating cycles. Any SVG or HTML element can be animated in this way. You can fine-tune your animation by adding other properties such as animation-timing-function which allows you the set the speed of the animation. Find out more at W3schools or Mozilla Docs.

## Animating with `stroke-dashoffset` property

When my animation starts, it looks as if a line was running on the circumference of the circle. To achieve this effect, I used 
'stroke-dashoffset' property.  A dashed stroke can appear like this:


However, it can also appear as a continuous line if the dashes are set to the length wider than the element. 

So I will only animate paths, rather than the whole element.  I have initially set the 'stroke-dashoffset' property to 1400 so that a continuous line appears at the beginning of the animation.

```css
svg circle {

  stroke-dasharray: 1400; 

  animation: 10s circle-outline infinite alternate;

  }

```

If you change this value to 100, it will appear as a dashed stroke (as the name implies). At 1400 the stroke fully covers the circumference of the circle, creating an illusion of movement.

```css
@keyframes circle-outline
{ 
   from {
    stroke-dashoffset: 1400;
            }
  to 
           { 
    stroke-dashoffset: 0;
           }
}
```
 
Want to learn more about SVGs? Head over to those links
@keyframers - Animate text on a scroll
JavaScript on SVGs


My pen : https://codepen.io/anka/pen/pJROva