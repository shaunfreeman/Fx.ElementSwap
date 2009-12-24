Fx.ElementSwap
==============

Fx.ElementSwap is a Slide Show class that will swap between any element using Fx.MorphElement to create the slide show effects.

Inherits methods, properties, options and events from [ElementSwap][].

![Screenshot](http://github.com/vincentbluff/Fx.ElementSwap/raw/master/screenshot.png)

###Extends
* [ElementSwap][]

Requirements
------------

* [MooTools Core 1.2.4](http://mootools.net/core): Class, Class.Extras, Element, Selectors, Fx.Morph, Fx.Transitions and their dependencies.
* [ElementSwap][] and their dependencies
* [Fx.MorphElement][] and their dependencies

How to use
----------

### Syntax
	#JS
	var myElSwap = new Fx.ElementSwap(elements[, options]);

### Arguments

1. elements - (*mixed*) A collection of elements to add. Takes the same arguments as [$$][]
2. options - (*object*, optional) An object with options. See [ElementSwap][] for options and below for extra options.

### Options
- TransitionFx - (*object*) see [Fx.MorphElement][] for available options. Defaults to:

	#JS
	{
		transition: 'linear',
		duration: 'long',
		onStart: function() {
			this.element.setStyle('overflow', 'hidden');
		},
		onComplete: function() {
			this.element.setStyle('overflow', 'auto');
		}
	}

- showFx - (*string*: defauts to 'slide:right') the fx to use when showing the slide.
- hideFx - (*string*: defauts to 'slide:left') the fx to use when hiding the slide
- wait - (*boolean*: defauts to true) whether to wait to execute the endFx after the startFx or run them together.

### Events
See [ElementSwap][] for all available events.

### Returns:

* (*object*) A new ElementSwap instance.

### Example:

### JavaScript

	#JS
	var elSwap = new ElementSwap('.div_swap');

### CSS

	#CSS
	#el1 {background-color:#f00;}
	#el2 {background-color:#0f0;}
	#el3 {background-color:#00f;}
	
	.div_swap {
		position:absolute;
		top:0px;
		width:300px;
		height:300px;
		z-index:0;
		display:none;
	}
	
	.active { display:block; z-index:1;}
	
	.elementSwap {
		position:relative;
		width:300px;
		height:300px;
		margin-left:auto;
		margin-right:auto;
		overflow:hidden;
	}

### HTML

	#HTML
	<div id="el1" class="div_swap"><p>DIV 1</p></div>
	<div id="el2" class="div_swap"><p>DIV 2</p></div>
	<div id="el3" class="div_swap"><p>DIV 3</p></div>

[$$]: http://www.mootools.net/docs/core/Element/Element#dollars
[ElementSwap]: http://www.mootools.net/forge/p/elementswap
[Fx.MorphElement]: http://www.mootools.net/forge/p/fx_morphelement
