#Woodhouse

Yet another fluid and responsive CSS grid system.

---

##Features

Woodhouse is just a CSS grid system. No really, that's it. There's not even a wrapper included to define a max-width. The syntax of Woodhouse is inspired by the [Zurb Foundation grid](http://foundation.zurb.com/docs/grid.php) and the math is inspired by the [tiny fluid grid](http://www.tinyfluidgrid.com/).

---

##Usage

Include woodhouse.css in your document's head like this:

```
<link href="/css/woodhouse.css" rel="stylesheet" />
``` 

Define a row with Woodhouse by using the "row" class. Columns are defined by applying to classes to an element. First the number of columns you want to span, followed by the class "columns". For example:

```
<div class="row">
	<div class="six columns">
		lorem ipsum
	</div>
	<div class="six columns">
		lorem ipsum
	</div>
</div> 
```

Woodhouse is a twelve column grid; this means that the columns in every row must add up to twelve. Woodhouse is also responsive. Once the browser width is less than 767px the columns will automatically stack atop one another. If you'd like a little more control, you can also define a separte column width for smaller screened devices. When collapsed, Woodhouse changes from a twelve column grid to a four column grid. For example:

```
<div class="row">
	<div class="six mobile-two columns">
		lorem ipsum
	</div>
	<div class="six mobile-two columns">
		lorem ipsum
	</div>
</div> 
```
