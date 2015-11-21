# Code like a designer
## Unity

What makes a design a design and not just a jumble of items on a page? What makes some pages feel more “tight” than others? Unity. 

### What is Unity?

Unity is a feeling of closeness, of cohesion, or being in the right place, among the elements in a design. The jumbled feeling you get when you look at some webpages, maybe even your own, is a lack of Unity in the design. 

#### Visual Unity vs Intellectual Unity

While a group of things may very much be related to each other (e.g. a group of photos from a wedding) they can be arranged in such a way that they still don’t feel like they belong together. This is the difference between Visual Unity and Intellectual Unity. Things that are thematically related at said to be intellectually unified. This kind of connection can aid in creating a unified design, but it isn’t a guarantee. 

Visual Unity is primarily what we’re concerned with here, and even a group of totally unrelated elements can be made to feel like they belong together. An important aspect of Visual Unity is the initial feeling that the whole is seen before the individual elements that make it up. If your first impression is that there is a bunch of things on a page and then you start to group them together, your page is lacking Visual Unity. 

The following techniques are ways to achieve Unity in your designs. 

#### Order vs Chaos
Like most things in design, and life, Unity is a force you must balance carefully against other characteristics of your design. Unity is in direct opposition with Variety, and too much or too little of either can have disastrous results. Too much Unity and a piece will feel mechanical, soulless, and boring. Things that are too unified tend to evoke people’s worst fears about conformity and a loss of individuality. Too much Variety and your piece will feel orderless, chaotic, jumbled, and random. Things with too much variety tend to evoke feelings of carelessness and lawlessness and generally feel “un-designed.” 

The challenge is to create Unity with enough Variety to not feel mechanical and boring, but still feel intentional and harmonious. Depending on what you’re trying to convey, your balance will change. 

### How to achieve Unity
For all of these examples we'll start off doing a classic 2d design exercise using a line, a square, and a circle. We'll create these shapes using some SVG markup. Here's how we do that.

We start out by opening an SVG element. Open the html-scaffold (or copy it into a new blank file) and inside the body tag add:

	<svg>

	</svg>

All of our SVG shapes will live inside the SVG tags. So far pretty simple. Next that's draw a line.

	<line x1="0" y1="0" x2="100" y2="100" />
	
The line tag lets us define a line to be drawn. The attributes are pretty simple once you know what they mean, x1 and y1 are the starting point from the top, left corner of the SVG element (in this case the top left corner of the screen.) x2 and y2 are the ending point. So here we've drawn a line that is staight up and down and 100 pixels tall. If we wanted the line to be horizontal, we could set y2 to 0 and we'd have a 100 pixel wide horizontal line. The line has a style attribute too, but we're going to do all our styling in CSS, so we've left it out here. Don't worry to much about the line's position right now, we'll use CSS to change that in just a bit.

Next let's draw our square.

	<rect width="200" height="200" />

The rectangle tag is much easier to understand than the line tag, IMO. Just like the line tag, the rectangle tag has a style attribute that we'll take care of in our CSS, so we've left it off here. Don't worry, we'll get to it. One last element to draw, our circle. 

	<circle cx="50" cy="50" r="40" />

I dislike this SVG tag the most, because the attributes are the least descriptive. cx and cy are the x,y coordinates of the center point of the circle. For this example I arbitratily picked 50 for both, because we're going to use CSS to move it around. r is the radius of the circle. If you remember your geometry, the radius of a circle is the distance from the center point to the edge, or half the width of the circle. (Bonus math points, the full width of the circle is called the diamiter.) So by setting r to 40 here we've created a circle that is 80 pixels wide. This is a friendly reminder that all of these languages were created by math nerds (and to be fair, computers are the ultimate math nerds, so it makese sense that's how we have to describe these things to a computer.)

All together your new code should now look like this:

	<svg>
		<line x1="0" y1="0" x2="100" y2="100" />
		<rect width="200" height="200" />
		<circle cx="50" cy="50" r="40" />
	</svg>

You are now ready to start experimenting with proximity. From here on out all the code we'll be writing will be in our CSS file. 


#### Proximity
Maybe the easiest way to achieve unity in a piece is through the use of proximity. Grouping like things closer together makes them feel like they belong together. Similarly putting a lot of space between things that are not a like makes them feel seperate. On the web, there are a few different ways we can acheive these effects: margins, padding, positioning and 2d transforms. NOTE: Placement and positioning is one of the most finickey parts of CSS, and this is a place where things may not be identical across browsers. Don't sweat it as long as they are pretty close. More importantly, there are multiple positioning models you can use in CSS. If you're using the HTML and CSS Scaffold files I've provided, you are using the border-box positioning model. I chose this because it makes more sense, but it is sadly not default. If this don't make any sense to you right now, don't worry about it, just make sure all of your CSS files start off with the first definition that my scaffold does and it will always work this way. If you want to learn more about differnet positioning models you can do so here (link to article about positioning needed.)

##### Margins
Margins are the space between the outside of elements in a webpage. 
##### Padding
##### Positioning 
##### Transform
#### Repetition
#### Continuation
#### Continuity

