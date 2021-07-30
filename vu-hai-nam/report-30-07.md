# === Enday 30/07 ===

## CSS

- Atomic CSS (tailwind - 20%)

    ### Definition

    - Basically, Atomic CSS is a way for writing CSS code so we dont need to write any single line of code. Thats mean we dont need to declare the CSS source anymore, just reuse the available classes which are previously declared before. Each class has their purpose and their properties (so that is the reason why it is called Atomic).

    - Tailwind is the most popular or universal CSS framework for building UI template quickly. In my opinion, this CSS Framework is a usefull, helpfull and convenient one in order to style website or template without writing any single line of CSS code. However, this is a new CSS framework for me so I think I need to spend large amount of time for adapting, no matter how you are good at CSS core, or remember clearly the syntax of CSS, you properly encounter the problems when using the Tailwind at the beginning. Because there lots of new class in Tailwind that are hard at remember even so, I do not deny that it is very easy and convenient to use.

    ### Application

    - I have just started read the documentations of Tailwind so I can be able provide the simplest example for the application of Tailwind. Imagine that you need to style a div block with all of these properties following, such as:

    ```CSS
        div {
            display: flex;
            text-align: center;
            color: red;
            background-color: blue;
            margin-top: 10px;
            /* and so on */
        }
    ```
    Usually, you will create a class and style it for a bunch of code like the css block above. But, instead of using this way we can use Tailwind by styling inline without any line of CSS code:

    ```HTML
        <div class="flex text-center bg-blue-900 mt-10 text-red">Hello World!</div>
    ```

## Issues

- In conclusion, Tailwind is really easy to use but when I tried to download and configure followed by documentations, that thrown some types of error (resolved). 
    -> But I have resolved these problems and got the support by Chien, he is a great teammate, always listens to me and helps me to find solutions for my problems. Im so grateful.