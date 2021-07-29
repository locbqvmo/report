## Nguyen Thi My report 29/07
**CSS Flexbox**
    Before the Flexbox Layout module, there were four layout modes:
    Block, for sections in a webpage
    Inline, for text
    Table, for two-dimensional table data
    Positioned, for explicit position of an element

    .flex-container {
        display: flex;
    
    }

   **Column**
    
    .flex-container {
        display: flex;
        flex-direction: column;
    } 
    The column value stacks the flex items vertically from top to bottom
    .flex-container {
        display: flex;
        flex-direction: column-reverse;
     }
    The column-reverse value stacks the flex items vertically (but from bottom to top)

   **Row**
    .flex-container {
        display: flex;
        flex-direction: row;
    }
    The row value stacks the flex items horizontally from left to right
    .flex-container {
        display: flex;
        flex-direction: row-reverse;
     }
     The row-reverse value stacks the flex items horizontally but from right to left
  
  **Flex Warp**
    .flex-container {
        display: flex;
        flex-wrap: wrap;
    }
    The wrap value specifies that the flex items will wrap if necessary
  
