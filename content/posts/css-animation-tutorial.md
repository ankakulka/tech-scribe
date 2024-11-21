---
title: "CSS Animation Tutorial"
date: 2022-11-29T16:02:35+01:00
draft: false
show_reading_time: true
tags: ['CSS', 'SVG', 'animation','coding']
category: Articles
toc: true
featured_image: "/images/leaf-lite.png"
omit_header_text: true
---

## Why create SVG animations using CSS?

Animations created with JavaScript (or animated gifs) can become heavy and cause web pages to load slowly. 
SVGs are light and can be either referenced or embedded directly in the code. The clue to another advantage of using SVGs is in the name - **S**calable **V**ector **G**raphics. 
They will look just as great on a tiny mobile screen as on a huge retina display.

Thanks to the animation features in CSS3 we can create simple (yet enticing!) animations that are easy on your page without the need to run JavaScript.

> This animation tutorial is suitable for everyone with basic HTML and CSS knowledge. 
> I will explain how to create a custom animation to create cool effects.
> You'll need a vector editing program and a text editor. 
 
We'll create the animation directly in the browser, in an online code editor [Codepen](https://codepen.io/).

## Create a simple vector image

This type of animation works best on simple images. I have created mine in Adobe Illustrator but open-source tools such as Inkscape will also do the trick. 
The most important thing is that you can save it as an SVG file.
Once you've saved your image as an SVG, open it in a text editor (such as Notepad, SublimeText or VS Code) and then select and copy all into clipboard.

## Create a pen in CodePen

Codepen is an online editor that allows you to create and share code snippets. I find it particularly useful for working with CSS animation as you can see the effects immediately, rather than having to constantly switch between the text editor and the browser as you would have to do when working locally. 
You don't even need to create an account! 

1. Select **CREATE** > **Pen** in the top left-hand corner.
2. Paste the code you copied from the text editor into the HTML section. 
    It should contain two sections - metadata, for example:
    - `xml version="1.0"`
    - main SVG section. Make sure you have the closing SVG tag `</svg>`.

### Basic SVG shapes

SVG is a subset of XML. Some basic SVG elements included in my image are:

  ```xml
<circle>
	<path>
		<line>
   ```

## Using CSS to animate

3. To make sure that my image sits perfectly in the middle of the screen, I can reference the SVG directly through the CSS rule:

```css
svg {
    position: absolute;
    margin: auto;
}
```

4. To animate individual parts of the image, start with the outermost layer - the circle. There's only one element in this image so I can use this as a selector without adding the element ID.

```css
svg circle {
    animation: circle-outline 10s alternate infinite;
}

```

The `animation` shorthand property allows me to define the most important features described by CSS properties:
- `animation-name`: 
    I named mine circle-outline, you can choose whatever you want for your animation.
- `animation-duration`: 
    the default is 0, so you have to specify how long the animation should be running for. 
    My animation lasts 10 seconds - I wanted to achieve a soothing effect, rather than a flashy one with a shorter cycle. 
- `animation-direction`: 
    specifies how the animation will be played: forwards, backwards or in alternate cycles. Mine runs in alternate cycles, so the stroke is going in one direction (forwards) then moves back on the loop.
- `animation-iteration-count`: 
    The infinite value specifies the number of times an animation should run. I want mine to run forever but you can also set the animation to just 1 or any other number.

5. To animate the opacity, use the `@keyframes` rule which controls the animation. 
This is where the animation takes place:

```css 
    @keyframes circle-outline {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
```

I have set the opacity to 0 in the first section so the shape is completely invisible, and to 1 which means it is fully visible (the values between 0-1 can be used or %). As the whole animation lasts 10 seconds, the image slowly appears on the screen, then slowly disappears as the animation is played back in alternating cycles.

6. When the animation starts, it looks as if a line was running on the circumference of the circle. To achieve this effect, I used `stroke-dashoffset` property. 
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
@keyframes circle-outline {
    from {
        stroke-dashoffset: 1400;
    }
    to {
        stroke-dashoffset: 0;
    }
}
```

## Summary

Any SVG or HTML element can be animated using these techniques. You can fine-tune your animation by adding other properties such as `animation-timing-function` which allows you the set the speed of the animation. 
To find out more check out these links:
- [W3schools](https://www.w3schools.com/css/css3_animations.asp)
- [Mozilla Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [CSS tricks](https://css-tricks.com/almanac/properties/a/animation/)

[My pen](https://codepen.io/anka/pen/pJROva)