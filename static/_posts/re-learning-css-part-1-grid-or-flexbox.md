---
layout: blog
title: 'Re-learning CSS Part 1: Grid or Flexbox'
date: 2020-05-01T16:03:45.390Z
headings: 'tutorial, learning, how to, how-to, css, html, web dev, web
  development, css-grid, grid, flexbox, layout, columns '
---

_TL;DR - CSS Grid and Flexbox are great. I use Grid for layouts and two-dimensional renderings, and Flexbox for one-dimensional renderings and components._

CSS is tough. When I started professionally developing websites about five years ago, there was zero incentive to develop CSS knowledge; even basic layouts seemed hacky, with prolific use of `float: right;` this and `margin: 0 auto;` that. It didn't intrinsically make sense and only added to the mystique and inapproachability that was CSS at the time.

Like many other software engineers at the time, I reached for CSS frameworks to solve the problem. I [Bootstrapped](https://getbootstrap.com/), [Bulma'ed](https://bulma.io/), and [Material Designed](https://material.io/) my way through a lot of them. Frameworks like these enable teams to develop products quickly and with a degree of uniformity. Professionally, I exclusively used frameworks for a long time, with the occasional tweak here and there in regular CSS. But frameworks are not without downsides: they can add a lot of weight to your package bundle, add complexity to your markup, and are yet another thing to learn.

I had all but resigned myself to working with frameworks forever, until I came across this tweet, in a thread discussing how a lot of folk (like me!) think CSS is a pain:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Modern CSS has solved so much of this. Come back to it with a fresh mind removing any remembrance of floats and Internet Explorer.</p>&mdash; Shaw (@shshaw) <a href="https://twitter.com/shshaw/status/1248095631077507073?ref_src=twsrc%5Etfw">April 9, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

This inspired me. Have I ignored major improvements in CSS? Is it easier now? Does it make more sense? What if _I_ come back to it with a 'fresh mind'?

And thus, this blog series was born. I'm going to relearn CSS and write about it along the way. I'll be looking at layouts, components, 'pure-CSS' images, and animations.

First up, layouts. Specifically, should I build my layout with CSS Grid or Flexbox?

## Grid or Flexbox?

According to our good friends at CanIUse (as of 8 May, 2020) both Flexbox and Grid work with the browsers a significant majority of people use.

![Can I Use CSS Grid](/uploads/can-i-use-grid.png 'Can I Use CSS Grid')

_[Can I use Grid?](https://caniuse.com/#feat=css-grid)_

![Can I use Flexbox](/uploads/can-i-use-flexbox.png 'Can I use Flexbox')

_[Can I use Flexbox?](https://caniuse.com/#feat=flexbox)_

While Grid has a bit more red in its image, it still works with the browsers 95% of the population use. For my audience, that works fine. If you need to accommodate for that remaining ~5%, I'd suggest adding appropriate polyfills.

## Building Layouts

Most layouts look something like this:

![A basic layout](/uploads/layout.png 'A basic layout')

I'd hazard a guess that a ridiculous proportion of websites have some form of this basic layout in place, with a header for title/nav/avatar, a footer for contact, external navigation, etc. two sidebars for whatever, and a main section in the middle. This layout is so popular, its been dubbed the ['Holy Grail' Layout](https://css-tricks.com/snippets/css/css-grid-starter-layouts/) by our pals over at CSS Tricks!

So, let's build this layout using both CSS Grid and Flexbox!

Here's the layout using Grid:

<iframe height="350" style="width: 70%;" scrolling="no" title="Basic Layout - Grid" src="https://codepen.io/jswiss/embed/BaorJOo?height=350&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/jswiss/pen/BaorJOo'>Basic Layout - Grid</a> by Joshua Swiss
  (<a href='https://codepen.io/jswiss'>@jswiss</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Overall, pretty simple! However, there are a few things worth noting, that may not be otherwise obvious:

- The element with `display: grid;` (here a `div` with the id of grid) sets top-level child elements of that div to exist in a grid display;
- `grid-template-rows` and `grid-template-columns` set up the grid. Here we have a 3x3 grid, with the header and footer set to 50px height, and the left and right sidebars set to 100px width;
- `grid-gap` is shorthand for `grid-column-gap` _and_ `grid-row-gap`. Here I set both to 1em;
- Similarly, `grid-column` is shorthand for `grid-column-start` and `grid-column-end`, where the grid item is not inclusive of the end column. Where I have `grid-column: 1 / 4;`, it means `grid-column-start: 1;, grid-column-end: 4;`, which means this grid item spans columns 1, 2, and 3.

Now, let's check out the same layout, this time using Flexbox:

<iframe height="350" style="width: 70%;" scrolling="no" title="Basic Layout - Flexbox" src="https://codepen.io/jswiss/embed/dyYmdWy?height=350&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/jswiss/pen/dyYmdWy'>Basic Layout - Flexbox</a> by Joshua Swiss
  (<a href='https://codepen.io/jswiss'>@jswiss</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

A little more verbose! I wrapped the second row in a `section` element so I could have rows inside columns (notice how Flexbox's rows/columns are the inverse of Grid's?). Let's break it down a little:

- For the topmost `div`, I set the display to flex, set a minimum height and width, and set the `flex-direction` to column. Column here means one column, with multiple rows;
- In the `#main` section, I again set the display to flex, and set `flex-direction` to row. Row here means one row, with multiple columns. I also gave the section a margin top and bottom of `1em`;
- I gave the header and footer and the asides default height and width; and
- I gave the main article a margin left and right of `1em`, and set it to `flex-grow: 1`. `flex-grow` allows the `article` element to expand to take up the extra space in the `flex-row` it is in.

### BONUS!

Here's the same layout using Bootstrap!

<iframe height="350" style="width: 70%;" scrolling="no" title="Basic Grid - Bootstrap" src="https://codepen.io/jswiss/embed/xxwWWqO?height=350&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/jswiss/pen/xxwWWqO'>Basic Grid - Bootstrap</a> by Joshua Swiss
  (<a href='https://codepen.io/jswiss'>@jswiss</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Funnily enough, even though I imported Bootstrap here, I'm _still_ using Flexbox! This is because Bootstrap uses the 12-column grid convention, and I _hate_ it. The 12-column grid layout is a web design convention that, at best, requires you to do some calculations, and at worst, requires you to overuse [magic numbers](https://css-tricks.com/magic-numbers-in-css/).

I cannot tell you how long I've spent fiddling with different configurations of the 12-column layout to get it just right; tweaking \`col-10\` to \`col-8\`, adjusting margins as I go. It's a waste of time, and you don't learn anything in the process.

So, if you still need Flexbox to use Bootstrap, why do you need to use Bootstrap. It's a very good question...

## Which to use?

In the end, I prefer Grid for layouts or anything two-dimensional, and Flexbox for one-dimensional renderings (like the icons in the bottom of my site!) or for components. Of course, that's personal preference; yours may differ, and mine may change over time!

For me, it is definitely time to rid myself of unnecessary frameworks, wipe the slate clean, and embrace CSS!
