# === Enday 29/07 ===

## HTML

- Semantic HTML (100%)
- Accessibility HTML (80%)
    
    ### Denfinition:
    
    - Basically, developers usually pay attention to build web application with many purposes such as: the web application can be able to found easily by SEO, the application can apply the newest or coolest framework in order to run fastly or stably. In a nutshell, we always take care of how to develop a product as quickly as possible, and assume that users also use the web like us and ignore the possibility that people with disabilities can use our website. So accessibility HTML is a way or standard that make our website can be easy to use for disabilities users.

    ### Application

    - There are many ways to increase the asseesibility of our website, but I will mention some of them.
    * Keyboard usability

        + Usual user can use the web with mouse. Instead of using the web with mouse like usual users, for some reasons the disabilities user cannot use the web with mouse so they have to use with keyboard like four arrow keys, tab/shift to move over, enter key for select.
        + At that time, we need to ensure that when the user move over the website by using tab key they wont focus on any meaningless things like a icon, button with no text on this (Because, they will use screen reader). So to deal with it, we should use ***tabindex*** to decide what element is the next to get focus.

    ### Semantic HTML:
    
    - With **<header>, <main>, <footer>, <section>, <table>, <form>** are really helpful for screen reader. Or we can use **role** global attribute for **<div>** tag in order tell to screen reader the pupose of this tag like **<div role="form">** 

    ### Color Contrast

    - There are many color standards, but the easiest one that we can apply is to not just use color to represent the state of button, always add some text. For instance, for switch button, just add some text like ON/OFF instead of just using colors.


*** 

## CSS

- Flexbox (80%)

    ### Definition

    - Flexbox is a layout mode, it can be able automatically and flexibility resize the elements inside the block. In orther word, we dont need to set the fixed size or set float of elements, just need establish it to display horizontally or vertically, then the elements inside can be displayed as we want.

    ### Application

    - For example, we want set three children elements can be display horizontally, and at the end instead the start of parents block.
    
    ```CSS
        .parents {
            display: flex;
            flex-direction: column;
            justify-content: flex-end:
        }
    ```

    In addition, if we want to resize the first child element that will have the rest of space in block. Normally, we will use online ruler tool or use developer tool to get the size of block parents and size of each child. After that, we do some minus expressions to find out the remaining space. However, when we use flexbox, we can set the first child with property flex equal to 1. flex property is a shorthand of three properties like flex-grow, flex-shrink and flex-basis:
    ```CSS
        .childs:first-child {
            flex: 1;
        }
    ```

***

## Responsive Web Design (70%)

   ### Definition

   - Responsive web design is a technique based on that website can be able to display compatible with many different screen size like PC, Tablet, Mobile. Or optimize the UX:
    * Display clearly elements (images, font size, button, ...)
    * Hide/Show elements according to the screen size.

    ### Application

    - Using **@meida** to limit the size screen. **@media** is a property or keyword that help we to select the size of screen and style for this size. For examp, we want to **<h1>** tag will have red color at PC, and have green color at Table.

    ```CSS
        /* 1240px for PC high resolution */
        @media (min-width: 1240px) {
            h1 {
                color: red;
            }
        }

        /* 740px to 1239 for Table and PC low resolution */
        @media (min-width: 740px) and (max-width: 1239px) {
            h1 {
                color: green;
            }
        }
    ```

    - Here we have **min-width** and **max-width** is a media features help us to select the specific size, **and** is a keywords that will select two features or clasue. Besides of that, in order change and style the size we need to add **<meta>** tag inside **<header>** tag in html file, like this:
    ```html
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```
    This gives the browser instructions on how to control the page's dimensions and scaling.

    - There are some other definitions that we need to mention like:
        1. **keywords**: 
            * not 
            * and
            * only
            * or
        2.  **media types**:
            * print
            * screen
            * all
        3.  **Breakpoint**
            * is a point, or size that will make the web's layout change or adapts to create responsive display
        4.  **Polyfill**
            * Help devs can be able to use media query with old browser like IE (6-9)

- Atomic CSS (0)