# 28/07

**HTML**

**_Semantic Html(70%)_**

- Semantic HTML is the correct use of HTML to reinforce the meaning of content on a web page.
- Semantic Elements in HTML:

  1.  HTML `<section>` Element:

      > - The `<section>` element defines a section in a document.
      > - More a `<section>` is a group of content width the same topic.

      ***

      > Ex:

           <section>
                <h1>Title content</h1>
                <p>Content</p>
                <ul>
                    <li>items1</li>
                    <li>items2</li>
                    <li>items3</li>
                </ul>
            </section>

  2.  HTML `<article>` Element:

      > - The `<article>` element specifies independent, self-contained content.
      > - These content can be cut out and taken elsewhere so that users elsewhere can still read it, regardless of the content containerd in the page.

      ***

      > Ex:

            <article>
                <h1>Title content</h1>
                <p>Content</p>
            </article>

  3.  HTML `<header>` Element:

      > - The `<header>` element represents a container for introductory content or a set of navigational links.
      > - A `<header>` element typically contains:
      >   - one or more heading element (`<h1>` - `<h6>`)
      >   - logo or icon
      >   - authorship information

      ***

      > Ex:

            <header>
                <div>
                    <img src="./Logo.png">
                </div>
                <h1>Title content</h1>
                <nav>
                    <ul>
                        <li>Home</li>
                        <li>About</li>
                        <li>Contact</li>
                    </ul>
                <nav>
            </header>

  4.  HTML `<footer>` Element:

      > - The `<footer>` element defines a footer for a document or section.
      > - `<footer>` element typically contains:
      >   - authorship information
      >   - copyright information
      >   - copyright information
      >   - sitemap
      >   - back to top links
      >   - related documents

      ***

      > Ex:

            <footer>
                <p>Author: Hege Refsnes</p>
                <p>
                    <a href="mailto:hege@example.com">hege@example.com</a>
                </p>
            </footer>

  5.  HTML `<nav>` Element:

      > - The `<nav>` element defines a set of navigation links.

      ***

      > Ex:

            <nav>
                <a href="/html">HTML</a>
                <a href=/css">CSS</a>
                <a href="/js">JS</a>
            </nav>

  6.  HTML `<aside>` Element:

      > - The `<aside>` element defines some content aside from the content it is placed in (like a sidebar)
      > - The `<aside>` content should be indirectly related to the surrounding content.

      ***

      > Ex:

            <div>
                <p>
                    My family and I visited The Epcot center this summer. The weather was nice, and Epcot was amazing! I had a great summer together with my family!
                </p>

                <aside>
                    <h4>Epcot Center</h4>
                    <p>
                        Epcot is a theme park at Walt Disney World Resort featuring exciting attractions, international pavilions, award-winning fireworks and seasonal special events.
                    </p>
                </aside>
            </div>

      In the report, there are references at: w3Schools

**_Html Accessibility(30%)_**

- HTML elements should use for their intended purpose as much as possible

---

**CSS**

**_Flexbox(35%)_**

- Flexbox is a layout mode that will resize the elements inside to display on all devices.
- Browers that support flexbox: Chrome 29+, Firefox 28+, internet Explorer 11+, Opera 17+, Safari 6.1, Android 4.4 +, ios 7.1.

- Flexbox properties:

  - Properties for the Parent (flex container)

    > Display:
    >
    > - To use Flexbox Layout need to set value for display property on large frame

        .container {
            display: flex;
        }

    **Flexbox Container Properties:**

    > flex-direction:
    >
    > - Arrange the elements in the container by column or row

        .container {
            display: flex;
            flex- direction: row | row-reverse | column | column-reverse;
        }

        -----------------------
        row (default):  left to right
        row-reverse:    right to left
        column:         same as row but top to bottom
        column-reverse: same as row-reverse but bottom to top
