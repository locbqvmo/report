# 30/07 
**Responsive Web Design**
> - Responsive is technique to make website display compatiable on many devices, different screen sizes.
> - Optimazing user experience : 
> - + Clearly show the component
> - + Hide/ Show the component suitable for screen sizes

    <style>
    .left, .right {
         float: left;
          width: 20%; 
    }

    .main {
        float: left;
        width: 60%; 
    }

    @media screen and (max-width: 800px) {
        .left, .main, .right {
            width: 100%; 
    }
    }
    </style>
