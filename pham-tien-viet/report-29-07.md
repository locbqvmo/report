# 29/07
**HTML**
> The `<article>` HTML element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable (e.g., in syndication). Examples include: a forum post, a magazine or newspaper article, or a blog entry, a product card, a user-submitted comment, an interactive widget or gadget, or any other independent item of content.
> ex : 
    <article class="day-forecast">
        <h2>03 March 2018</h2>
        <p>Rain.</p>
    </article>
> The `<aside>` HTML element represents a portion of a document whose content is only indirectly related to the document's main content. Asides are frequently presented as sidebars or call-out boxes.
> ex : 
    <aside>
        <p>Where everyone knows</p>
    </aside>
> The `<details>` HTML element creates a disclosure widget in which information is visible only when the widget is toggled into an "open" state 
> ex :
    <details>
        <summary>Details</summary>
        Something you knows
    </details>

> The `<figcaption>` HTML element represents a caption or legend describing the rest of the contents of its parent `<figure>` element.
> ex :
    <figue>
        <img abcxyz>
        <figcaption> This is notice </figcaption>
    </figure>

**CSS** 

> Colum or rows
 .flex-container {
     display: flex;
     flex-direction: column/row-reverse/column-reverse;
     background-color: DodgerBlue;
}
> flex-flow shorthand
 .flex-container {
     display: flex;
     flex-direction: column/row-reverse/column-reverse;
      flex-flow: row wrap; `flex-direction: row; flex-wrap: wrap; `
     background-color: DodgerBlue;
}
> Flexible sizing of flex items
    article {
        flex: 1 200px;
    }

    article:nth-of-type(3) {
        flex: 2 200px;
    }
> The justify-content Property
    .flex-container {
      display: flex;
      justify-content: center/flex-start/flex-end/space-around/space-between;
    }
> The align-items Property
    .flex-container {
        display: flex;
        height: 200px;
        align-items: center/flex-start/flex-end/stretch;
    }
**Atomic CSS**
TailwindCSS