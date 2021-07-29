# 28/07
**HTML**
Semantic Html does not only provide meaning to content elements, it also provides the foundation for elements' interactivity
Semantic Element : 

> The `<footer>` HTML element represents a footer for its nearest sectioning content or sectioning root element. A `<footer>` typically contains information about the author of the section, copyright data or links to related documents.
> ex :
    <footer>
        <p>VMO 2021</p>
    </footer>

> The `<header>` HTML element represents introductory content, typically a group of introductory or navigational aids. It may contain some heading elements but also a logo, a search form, an author name, and other elements.
> ex :
    <header >
        <h1>Cute Puppies Express!</h1>
    </header>

> The `<body>` HTML element represents the content of an HTML document. There can be only one `<body>` element in a document.
> ex : 
    <html>
    <head>
        <title>Document title</title>
    </head>
    <body>
        <p>This is a paragraph</p>
    </body>
    </html>

Html Accessibility :  HTML elements should use for their intended purpose as much as possible.
**CSS** 
FlexBox : help Dev set a special value of display on the parent element of the elements you want to affect
    section {
        display: flex;
            }
> The flex model:
> - The main axis is the axis running in the direction the flex items are being laid out in. The start and end of this axis are called the main start and main end.
> - The cross axis is the axis running perpendicular to the direction the flex items are being laid out in. The start and end of this axis are called the cross start and cross end.
> - The parent element that has display: flex set on it (the `<section>` in our example) is called the flex container.
> - The items being laid out as flexible boxes inside the flex container are called flex items (the `<article>` elements in our example).
