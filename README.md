#Woodhouse

Sass Grid Generator Extrodinaire.

---

##The Elevator Pitch

Woodhouse is a responsive mobile-first Sass grid generator. With a few variable tweaks you can control every aspect of your grid to ensure it fits your needs exactly. 

##Fractions

Unlike traditional twelve or sixteen column grids, Woodhouse grids are based on fractions. For example 1-2 would be 1 over 2, or one half, meaning that that element would take up exactly one half of the total width available to it. By default Woodhouse supports whole (1-1), halves (1-2), thirds (1-3), and quarters (1-4) but you can very easily add support for more granular grids based on your needs. Woodhouse will automatically generate support for all parts of a fraction, for example three quarters would be written as 3-4.

##Breakpoints

Woodhouse is a mobile first grid system meaning that it works best when you start developing the mobile view before developing the larger views. Rather than basing Woodhouse on a few device specific breakpoints, it is designed to allow you to add breakpoints as your design requires them. Start small, widen your screen until your site looks whack, add a breakpoint to fix it, rinse and repeat. For more info on mobile first design and development check out [Luke Wroblewski's Mobile First](http://www.abookapart.com/products/mobile-first).

##Elements

###Grid Elements

The main building blocks of Woodhouse are the grid elements. Grid element naming consists of a breakpoint name followed by a dash followed by the size of the element. For example, let's say you have a breakpoint named 'palm' and you'd like your element to occupy the full width at said breakpoint, the syntax would be as follows:

```
<div class="palm-1-1">...</div> 
```

Now, let's say you have another larger breakpoint named 'lap' and you'd like the same element to occupy half the width when that breakpoint is reached. The element would be modified as follows:

```
<div class="palm-1-1 lap-1-2">...</div> 
```

As you can see from the example above, larger breakpoints will override smaller ones.

###Show/Hide

In addition to the grid elements, every breakpoint will also have a show and hide modifier. "Show" means display this element at this breakpoint but hide it in lesser breakpoints. "Hide" means show this element until this breakpoint is reached. Like grid elements, show/hide elements begin with a breakpoint name followed by a dash followed by either "show" or "hide". For example:

```
<div class="palm-1-1 lap-hide">...</div>
```

###Group

Group elements are used to group grid elements together. A group is similar to a row in a more traditional grid system, however since rows may vary from breakpoint to breakpoint, the name "row" would not be very semantically correct in this circumstance. Unlike the grid and show/hide elements, group elements are not breakpoint specific. You would implement the group element like this:

```
<div class="group">
	<div class="palm-1-1 lap-1-3">...</div>
	<div class="palm-1-1 lap-1-3">...</div>
	<div class="palm-1-1 lap-1-3">...</div>
</div>
```

###Container

The container element is the outermost wrapper element. The only job of the container element is to ensure that your site is horizontally centered on the page when being viewed beyond its maximum width. Like the group element, the container element is not breakpoint specific and would be implemented as follows:

```
<div class="container">...<div>
```

---

##Getting started

1. Move "_woodhouse.scss" into your website directory (I like to put it and all scss files in thier own "scss" folder but you can put it wherever you'd like).
1. Import Woodhouse at the beginning of your main Sass file like this "@import 'woodhouse'".
1. Compile your Sass to CSS.
1. Start using Woodhouse in your HTML.

For more info on working with Sass visit the [Sass Tutorial](http://sass-lang.com/tutorial.html). If Terminal terrifies you, there are also many applicaitons that will handle Sass compilation, here are a few you might want to check out: [CodeKit](http://incident57.com/codekit/), [Compass.app](http://compass.handlino.com/), [LiveReload](http://livereload.com/), [Hammer](http://hammerformac.com/), [Mixture](http://mixture.io/), and [Scout](http://mhs.github.com/scout-app/).

---

##Working with Parameters

Woodhouse has a number of paramaters availabe that allow you to tweak it to fit your exact needs. If you'd like to modify any Woodhouse parameters be sure to do so in your Sass file that imports Woodhouse rather than modifing the paramaters in "_woodhouse.scss" directly. For example, if you'd like the maximum width to be 960px instead of the default 1200px you would set the parameter before you import Woodhouse, as follows:

```
$wh-max-width: 960px;
@import 'woodhouse';
```

##Available Parameters

**$wh-breakpoint-names: palm, lap, desk !default;**
**name:** wh-breakpoint-names
**info:** a comma separated list of your breakpoint names. As other woodhouse classes will use these names as a prefix ensure that none begin with numbers.
**type:** comma separated strings

**$wh-breakpoints: 0px, 480px, 850px !default;**
**name:** wh-breakpoints
**info:** a comma separated list of your breakpoint values. Though not required it is highly recommended that the first value be 0. It is important to ensure that both wh-breakpoint-names and wh-breakpoints contain the same number of values.
**type:** comma separated values

**$wh-fractions: 4 !default;**
**name:** wh-fractions
**info:** represents the smallest fractions Woodhouse will accommodate. For example at 4 Woodhouse will handle up to and including quarter units. Larger numbers will allow for more granular grids but will result in larger files.
**type:** integer 

**$wh-gutter: 2% !default;**
**name:** wh-gutter
**info:** the size of the gutters (space between grid sections). 
**type:** percentage

**$wh-max-width: 1200px !default;**
**name:** wh-max-width
**info:** the max width of your website. This width is applied to the container. 
**type:** pixels

**$wh-group-name: group !default;**
**name:** wh-group-name
**info:** the class name to use for the group element. 
**type:** string

**$wh-container-name: container !default;**
**name:** wh-container-name
**info:** the class name to use for the container element. 
**type:** string
