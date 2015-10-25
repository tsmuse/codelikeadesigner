# Code like a designer
## The basics

### Web code basics
The web is, largely, made up of Hypertext and code modifying that hypertext. While I don’t intend to cover coding the way most coding books do, there is a little bit of setup that can’t be avoided. This is the most “traditional programming class” part, and it’s because it largely can’t be avoided. I’ve tried to explain why things are the way they are, without going into some of the fairly arcane rational behind some of these things that is, for the most part, largely irrelevant to your work as a designer. In those instances, you just have to accept that this is the way this technology works right now, memorize it, and keep moving. Desktop publishing apps like Photoshop have a TON of things that work that way, and you’ve probably internalized all of them at this point without thinking too much about it. 

#### Hypertext Markup Language (HTML)
To create hypertext, you need to take regular text and mark it up. That’s what HTML is all about. To create an HTML document, you simple create a blank text document and add the following to it:
	
	<!DOCTYPE html>
	<html>
		<head>
		</head>
		<body>
		</body>
	</html>

Save it as a .html file and that’s it, you’ve created HTML! All the content and elements for any thing we make will live inside this framework. 

##### `<head>` tag
This is where all the setup information about the document lives. We’ll add more to this part of the document later. Do not confuse this with the document’s header. 

##### `<body>` tag
This is literally the “body” of the document. It’s where all the content lives. 

##### HTML tags
You may have noticed, all the “tags” that make up HTML live inside < >. You use the tags by wrapping your content in them, usually by opening a tag and then closing it.

	<tag> this is some content </tag> 

Tags can also have attributes, which you set using the = sign:
	
	<tag attribute=“something”> this is some content </tag>

Some tags don’t wrap text and don’t have a closing tag. These are called “self-closing tags.” Images are the most common self-closing tag. 
	
	<img src=“somefile.gif” alt=“this is a gif!”/>

If this all seems very simple, that’s because it is. Wrap your text in the right tag, and you have a web page. It really is just that easy. 

##### Classes and IDs
Every HTML tag has a list of common attributes. The most important ones for you to know are class and id, because they are used by CSS to create and modify the styles of HTML tags.
 
###### Class
You can think of a class as a group. A 5th grade class is a group of students that all have a teacher in common. An HTML class is a group of tags that all have a class attribute in common. Classes are super useful when you’re working on styling things, as they let you select a specific group of elements to style the same way, even if those elements aren’t all wrapped in the same type of HTML tag. You assign a tag to a class by setting it’s class attribute equal to the name of the class or classes it is in.

	<img class=“album-photos” src=“photo1.jpg” alt=“Kitten Photo 1”/>

A tag can also be in multiple classes at once, you just separate the class names with a space
	
	<img class=“album-photos funky-border” src=“photo1.jpg” alt=“Kitten Photo 1”/>

###### ID
An ID is a unique name for a specific HTML tag. If you have a logo image on a page full of other images, and you want to be able to refer to that logo the easiest and best way to do that is by giving that specific image tag an ID. That way you can specifically style the logo differently than the rest of the images on the page. Just like with a class, you assign an ID to a tag by setting it’s id attribute to the ID you want to use

	<img id=“logo” src=“logo.png” alt=“Sloth Corp Logo”/>

##### Basic HTML tags you just need to memorize
There are a few tags that you will use A LOT, so we’re going to get them out of the way here.

###### `<div>`
The div tag is the most used tag in modern web layouts. It defines a container (think a square area) that you put text and other tags in. You can use it to create basic rectilinear shapes, but it’s most often used as a container. 

	<div>
		Here is some stuff inside a this div. 
	</div>

###### `<p>` (Paragraph)
The paragraph tag is very similar to the <div> tag, but it has some padding built into it to make text readable. You use it to break up paragraphs of text. 

	<p>
		World’s shortest paragraph.
	</p>

###### `<a>` (Anchor)
The anchor tag makes hyperlinks, what most people just call links. This is an important distinction to make because there is a link tag and it links code together. If you’re having a hard time keeping them straight, just think about this tag creating “*a* link.” This tag has an important attribute to memorize, mainly the destination of where the hyperlink leads to. That attribute is called “href” which stands for hyperlink-reference and you’re just going to have to live with the name that doesn’t make sense anymore. 

	<a href=“http://www.codelikeadesigner.com”> some link text </a>
###### `<img>` (Image)
The image tag thankfully does exactly what it’s name implies, it places an image in your page. It even has two friendly named attribute that you need to remember: src (source of the image aka where the image file is) and alt (the alternate text to display if the image can’t be loaded.) Remember that image tags are self-closing.

	<img src=“someGif.gif” alt=“this is a gif of kitties”/>

There are a lot more tags, but we’ll cover them as we’re talking about different design techniques. 

#### Cascading Style Sheets (CSS)
Because nothing in this world is easy, you can’t just use HTML to create a website anymore. If you want to make it look like more than just text on a page, you have to use another programming language to do that (actually, you have to use more than one.) CSS is the language of styles. While you can put your  CSS into your HTML file, that is generally frowned upon, and so we’re going to just put ours into a separate file. Creating a CSS file is really easy. Create a new text file and then add:
	
	@charset “utf-8”;

Save it as a .css file and that’s it! You have a blank style sheet. 

##### CSS styles
Like HTML has tags, CSS has styles. Unfortunately CSS styles are nothing like HTML tags, but all styles follow a basic format

	element-selector{
		property: value;
		property: value;
	}

Styles come in four varieties: ID styles, Class styles, Special Selector styles, and Element styles. They all follow the above pattern, the only difference is the part outside the brackets.

###### Element styles
Element styles effect an HTML tag. You just use the html tag you want to style, minus the < >’s

	div{
		property: value;
	} 

This style will effect every <div> element in your document. 

###### Class Styles
Sometimes you don’t want to style every instance of a specific tag in a document…like most times. A class style lets you create a style that can be applied to multiple tags, as long as they are part of that “class.” Think of a class like a group. To create a class style you give your class a name, and then put a . in front of it

	.my-awesome-class{
		property: value;
	}

This style will only apply to members of the my-awesome-class class. 

###### ID Styles
Sometimes you just want to style one unique thing, and nothing else. Those are the times you want to use an ID style. IDs are like names, there can only be one of them in your design. To create an ID style, you put a # before the ID you want to style

#unique-ID{
	property: value;
}

This style will only apply to the one element with the ID “unique-ID.”

###### Special Selector styles
For the most part, between element, class, and ID styles you will be able to create whatever you need for your design. However, sometimes you need to do some things that are a little wacky. Selectors make it easier to do that wacky stuff. This comes in most handy when you are styling elements that are going to be created by a computer algorithm and not you (it happens more often than you’d think.) CSS has a long list of special selectors that you can use to do some really cool things, like select the odd numbered things in a group. Most selectors start with : and they work just like all the other styles

	:special-selector{
		property: value;
	}

You can read more about special selectors here, but if they are confusing to you right now, don’t worry about it. It will all make sense soon.

##### Linking the files together
Remember when I said there was a link tag that links files together? That’s the tag we use to get our CSS to actually manipulate our HTML. The `<link>` tag has three attributes to remember: 
* src —— the location of the css file
* rel —— the relevance of the link to this HTML document. This will always be “stylesheet” when we’re linking stylesheets. 
* type —— the type of the file we’re linking to, this will always be “text/css” when we’re linking stylesheets.

From our basic HTML document before we will add one line:

	<!DOCTYPE html>
	<html>
		<head>
			<link src=“stylesheet.css” rel=“stylesheet” type=“text/css”/>
		</head>
		<body>
		</body>
	</html>


#### Scalable Vector Graphics (SVG)
While you could just use HTML, CSS and some image files to create and style your pages, image files can be large, and they don’t always scale well. SVG lets you create fairly simple images in web-native code, that load faster and resize well in most modern web browsers. You’ll see some SVG in the examples, and sometimes the best way to create a complicated SVG is to use a tool like Adobe Illustrator or Sketch, and paste the code into your HTML. 

For now, all you really need to know is that SVG drawing instructions live inside the `<svg>`, are formatted like HTML, and mostly get styled using the same CSS as HTML. 


That’s it for the technology basics, let’s talk about the design basics we need to know. 

### Digital design basics

The user-facing elements of modern software largely borrow the fundamental elements of graphic design, which are: 
* Line
* Shape
* Space
* Value
* Color
* Texture

#### Space
Space is the entirety of the area of a composition, be it a piece of paper or the viewport in a web browser. We can divide space into two distinct kinds: positive and negative. Positive space is the space in a composition that has something in it. It is what most people think of when they think of graphic design, it’s the things on the page/screen. Negative space is all the empty space. Negative space is a crucial element in graphic design and should be considered just as carefully as the positive space in your compositions.
#### Line
A line is, at it’s most basic, the distance between two points. The first thing you probably think of when you think of a line is a solid mark with starting and an ending points, in graphic design speak “a rule”. Lines can also be made by arranging elements in such a way as to create the feeling of a continuous line, or you may leave a certain amount of blank space to create a line, like the gutters in-between panels in a comic book. Both of these uses are “implied lines” 

#### Shape
A shape is a closed line, we know most shapes by their outlines, but shapes are more than just areas of value or color. Text, photographs and interactive elements are often arranged into and moved around a composition as shapes.

#### Value
Value is the measure of how light or dark something is on a scale from pure white to pure black. Everything in your composition has a value, including any colors you use. 
#### Color
As value is the measure of lightness or darkness, color is at it’s most basic a measure of hue; how red, green, blue, orange, yellow, indigo, or violet something is. When you think of a specific color you are likely thinking of a combination of value and hue that makes up that color. 

#### Texture
Texture is a tactile surface, or the impression of one. In digital design texture is most-often created by repeating patterns made of simple shapes or lines. Typography, illustrations, and photographs also add texture to a composition. 

In addition to the fundamental elements of graphic design, when we’re designing for the web or native software platforms there are a few other fundamental elements specific to the medium: time and sound. 

#### Time
While traditional graphic design is focused on printed media, time does not play a key role outside of the sequence of individual pieces. When we change the medium to software, suddenly time becomes a key component of any design we create. Digital interfaces react to user input, move to reveal hidden elements or add emphasis, and are even assembled over time as opposed to being presented all at once. Like the other fundamental elements, the use of time should be considered very carefully in your designs. 
 
#### Sound
	Graphic design is primarily visual. Current trends in computing make most interfaces primarily visual, although the use of sound to reenforce interactions (like the *click* most soft-keyboards make on most smartphones) that are primarily visual and add a sense of texture. As computing becomes more ubiquitous, sound is becoming more than just an element of texture, it is also becoming the primary interface. Consider carefully both the sounds your interface will make as well as the sounds your users will make in your designs.   

Every digital design you make will will consist entirely of these fundamental elements. Understanding them is key because every line of code you write will either be creating or manipulating them. 

By combining the technology and design fundamentals you are now ready to approach learning how to code for the web thinking like a designer (or perhaps approach learning graphic design with the tools of a developer.)