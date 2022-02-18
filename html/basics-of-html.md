# Basics of HTML

## HTML Anatomy

HTML is the structure of the content that goes inside the tags. Browsers provide default style, but it's not very visual. HTML documents use `<tag>` to tell the browser how to format the content.

HTML is composed of [elements](https://www.codecademy.com/resources/docs/html/elements?page\_ref=catalog). These elements structure the webpage and define its content.

![Opening & Closing Tags](https://cdn.rawgit.com/MakeSchool-Tutorials/sa-2018-landing-page/master/P02-HTML-Basics/assets/html\_element\_breakdown.png)



HTML stands for HyperText Markup Language:

* A _markup_ language is a computer language that defines the structure and presentation of raw text.
* In HTML, the computer can interpret _raw text_ that is wrapped in HTML elements.
* _HyperText_ is text displayed on a computer or device that provides access to other text through links, also known as _hyperlinks_.&#x20;

## HTML Structure

HTML is organized as a collection of family tree relationships.

![HTML DOM Structure](<../.gitbook/assets/image (1).png>)

When an element is contained inside another element, it is considered the _child_ of that element. The child element is said to be _nested_ inside of the _parent_ element.

## The Body

One of the key HTML elements we use to build a webpage is the _body_ element. Only content inside the opening and closing body tags can be displayed to the screen.

```
<body>
  <p>The text here will appear on the screen.</p>
</body>
```

## Headings

Headings are used to describe content, like the title of a movie or an educational article. The following is the list of heading elements available in HTML. They are ordered from largest to smallest in size.

1. `<h1>` — used for main headings. All other smaller headings are used for subheadings.
2. `<h2>`
3. `<h3>`
4. `<h4>`
5. `<h5>`
6. `<h6>`

## Divs

`<div>` is short for “division” or a container that divides the page into sections. These sections are very useful for grouping elements in your HTML together. It allow us to group HTML elements to apply the same styles for all HTML elements inside. We can also style the `<div>` element as a whole.



## Attributes

Attributes are content added to the opening tag of an element and can be used in several different ways, from providing information to changing styling. Attributes are made up of the following two parts:

* The _name_ of the attribute
* The _value_ of the attribute

## Displaying Text

To display text in HTML, we can use a _paragraph_ or _span_:

* _Paragraphs_ (`<p>`) contain a block of plain text.
* `<span>` contains short pieces of text or other HTML. They are used to separate small pieces of content that are on the same line as other content.

## Styling Text

You can style text using HTML tags:

* The `<em>` tag will generally render as _italic_ emphasis.
* The `<strong>` will generally render as **bold** emphasis.

## Line Breaks

The spacing between code in an HTML file doesn’t affect the positioning of elements in the browser. To modify the spacing in the browser, you can use HTML’s _line break_ element: `<br>`.

## Lists

In HTML, you can use an _unordered list_ tag (`<ul>`) to create a list of items in no particular order. An unordered list outlines individual _list items_ with a bullet point.

_Ordered lists_ (`<ol>`) are like unordered lists, except that each list item is numbered. They are useful when you need to list different steps in a process or rank items for first to last.

## Images

The `<img>` tag allows you to add an image to a web page. Most elements require both opening and closing tags, but the `<img>` tag is a _self-closing tag_.

```
<img src="image-location.jpg" />
```

The `<img>` tag has a required _attribute_ called `src`. The `src` attribute must be set to the image’s _source_, or the location of the image. In this case, the value of `src` must be the _uniform resource locator_ (URL) of the image. A URL is the web address or local address where a file is stored.

```
<img src="#" alt="A field of yellow sunflowers" />
```

The `alt` attribute, which means alternative text, brings meaning to the images on our sites. The `alt` attribute can be added to the image tag just like the `src` attribute. The value of `alt` should be a description of the image.

The `alt` attribute also serves the following purposes:

* If an image fails to load on a web page, a user can mouse over the area originally intended for the image and read a brief description of the image. This is made possible by the description you provide in the `alt` attribute.
* Visually impaired users often browse the web with the aid of screen reading software. When you include the `alt` attribute, the screen reading software can read the image’s description out loud to the visually impaired user.
* The `alt` attribute also plays a role in Search Engine Optimization (SEO), because search engines cannot “see” the images on websites as they crawl the internet. Having descriptive `alt` attributes can improve the ranking of your site.

## Videos

HTML also supports displaying [videos](https://www.codecademy.com/resources/docs/html/videos?page\_ref=catalog). Like the `<img>` tag, the `<video>` tag requires a `src` attribute with a link to the video source. Unlike the `<img>` tag however, the `<video>` element requires an opening and a closing tag.
