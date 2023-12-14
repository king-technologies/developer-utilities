# Css

## Css Selectors

- Basic selectors target HTML tags such as h1, p and img tags. When you target the root tag, any styling you apply becomes part of the ‘global’ style.
- :hover : This will save you the trouble of tracing selectors and their properties as your CSS styling grows.
- You can also target specific blocks of your HTML via class and id selectors. Ids are expected to only be used once and nowadays, are often reserved for JavaScript hooking. Classes are often a more standard method of HTML blocks and are more reusable in nature than ids.
- Adjacent sibling selection combination: In the DOM, tags that sit directly next to one another are called siblings. This means that h1 and p are siblings, but h1 and ul are not. Siblings need to be right next to each other, or else putting down h1 + ul will hit on every possible ul that exists, regardless of proximity.
- When you use the + sign, you can create selection conditions. It tells your browser to select adjacent siblings — that is, a combination pair of elements that sits directly next to another specified element.
- Child combinations select elements that are direct children of the target element. > is used to denote this condition.
- Attribute Selectors: Attribute selectors target HTML through their attributes. HTML attributes are specific to particular elements only and enrich the HTML with extra meta information. They are targeted through the target element followed by the associated data surrounded by [ ] Here are some common and useful attribute selectors that are targeted through HTML attributes.
- a[href*=”twitter”] — Targets `<a>` elements that have href value that contains the word “twitter”. Example: `<a href=”http://twitter.com">Twitter</a>`
- `a[href^=”https://”]`  — Targets `<a>` elements that have a href value that starts with `http://`
  Example: `<a href=”https://dottedsquirrel.com">Dotted Squirrel</a>`
- a[href$=”.co”] — Target `<a>` elements that have an href value that ends with .co
  Example: `<a href=”website.co”>Company & Co</a>`
- button[disabled] — Targets button elements that have disabled attribute applied Example: `<button type=”button” disabled>Click Me!</button>`
- input[type=”submit”] — Targets input elements if they have a type attribute with an exact value of submit
- Pseudo-Elements: Pseudo-elements target the ‘space’ before and after an element. The actual space doesn’t exist as such in HTML but CSS inserts an empty container, giving you a space to manipulate.
- .item:before { content: “icon.jpg”; }
- .item:after { content: “anotherIcon.jpg”; }
- :before and :after pseudo-elements are often used to display special preceding items such as icons. For pseudo-elements, the content property is required but can be left blank. They are treated like any other element and can be styled accordingly.
  Here are two other pseudo-elements that can come in handy with `<p>` tags. The following pseudo-elements require :: because they only work in some browsers and need the entire set for it to work properly. They only work on some because it’s currently being implemented across the broad.

## Open Source Css Frameworks

- [Bootstrap](https://github.com/twbs/bootstrap) The most popular CSS framework; by Twitter
- [PatternFly](https://github.com/patternfly/patternfly) Open source framework; by Red Hat, PatternFly is primarily focused on enterprise application developers and provides components, such as bars, charts, and navigation, that are very appealing for creating powerful, metrics-driven dashboards.
- [Material Components for the Web](https://github.com/material-components/material-components-web) Open source framework; by Google
- [Pure](https://github.com/pure-css/pure) Open source framework; by Yahoo
- [Foundation](https://github.com/foundation/foundation-sites) Frontend framework; by Zurb Foundation
- [Bulma](https://github.com/jgthms/bulma) Modern CSS framework based on Flexbox
- [Skeleton](https://github.com/dhg/Skeleton) Lightweight CSS framework. The Skeleton library is only about 400 lines long, and the framework provides only the essential components to start your CSS framework journey.
- [Materialize](https://github.com/Dogfalo/materialize) CSS framework based on Material Design
- [Bootflat](https://github.com/bootflat/bootflat.github.io) Open source Flat UI kit based on Bootstrap 3.3.0

## Tab Size

> Most code editors are equipped with Tab size control that allows developers to specify the code indentation width made with the tab key. You are also able to customize the indentation of the code embedded on webpages.

```CSS
pre{tab-size:4;}
```

## Pointer Events

> The Pointer-events property allows us to control element behavior under pointer events like dragging, hovering and clicking. in Following example, the affected link will do nothing when it is clicked; the link will be completely disabled

```CSS
a{pointer-events:none;}
```

## Image Orientation

> Like in an image editor, now you change the image orientation by rotating or flipping the images with CSS. here is an example on how we can flip and image horizontally using this property

```CSS
img{image-orientation:flip;}
```

## Text Rendering

> This property will tell browsers how they should render the text within webpages. The text will be optimized for performance, legibility, or precision, which will eventually determine the text quality.

```CSS
p{text-rendering:optimizedLegibility;}
```

## Image Rendering

> Image-rendering defines the image quality on webpages, in particular when the image is forcefully resized. With the advent of this property comes a number of new values, and browsers have their own specifications in this matter

```CSS
img{image-rendering:crisp-edges;}
```

## Writing Mode

> Not every language is written from the left to right direction some languages are instead written from top to bottom or right to left. To accommodate these languages, writing-mode is introduced to let developers change the context writing direction through CSS

```CSS
p{writing-mode:rl-tb;}
```

## Text Overflow

> The text-overflow property specifies presentation of content that is overflowing or truncated by its container. The default value is to set to **clip** which simply hides the truncated text. You can set it to **Ellipsis** to depict the truncated text or content with horizontal ellipsis.

```CSS
.context-box{text-overflow:ellipsis;}
```

## Font-variant-numeric

```CSS
.context-box{font-variant-numeric: Slashed-zero;}
```

## Scroll-behavior

```CSS
.context-box{Scroll-behavior: smooth;}
```

## font property

```CSS
h1{font:normal 16px Arial;
line-height:1.6em;
text-decoration:underline;
text-transform:uppercase;
letter-spacing:0.2em;
word-spacing:0.2em;}

```

## Margin Padding

```CSS
.box{margin: top, right, bottom,left;
margin:top-bottom,left-right;
border-radius:15px;}
```

## links

```CSS
a{
  text-decoration:none;
  color:#000;
}
a:hover{
  color:red;
}
a:active{
  color:green;
}
a:visited{
  color:yellow;
}
```

## list

```CSS
li{
  list-style-image:url('check.png');
}
```

## box

```CSS
.block{
  float:left;
  width:33.3%;
  border:1px solid #ccc;
  padding:10px;
  box-sizing:border-box;
}

.clr{
  clear:both;
}
```

## position

```CSS
.p-box{
  width:800px;
  height:500px;
  border:1px solid #000;
  margin-top:30px;
  position:relative;
}

.p-box h1{
  position:absolute;
  top:100px;
  left:200px;
}
```

## sudo classes

```CSS
.my-list li:first-child{
background:red;
}
.my-list li:last-child{
background:green;
}
.my-list li:nth-child(5){
background:blue;
}

.my-list li:nth-child(even){
background:blue; 
}
```

## Media Queries

```CSS
@media (prefers-color-scheme: dark) {
   :root{
     color-scheme:light dark;
   }
}
```
