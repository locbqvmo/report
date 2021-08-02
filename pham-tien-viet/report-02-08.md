# 02/08 
## Javascript
> **Scope and Closure**

>  **Scope**  : is the operating limit of a variable or a function . Have 3 type of Scope .

> - + Global Scope : To used the all of file

>  Ex:

    const a = {1,2,3};
    var b = 6;
    let c = "tienviet"

> - + Code Block : part of the code is wrapped up in the program : let, const

> Ex :

    {
        const a = {1,2,3}; 
    }

    function logger(){
        let c = "tienviet"
        console.log(c)
    }

    if (true){
        const a = {1,2,3}; 
    }


> - + Local scope : variable or function declared in the code 

> Ex:

    for (i:=1;i<5;i++){
        const b=1;
        a:=+b
    }

> - When calling each function, a new scope is created 

> Ex : 

    function logger(){
        let c = "tienviet"
        console.log(c)
    }

    logger();

> - Functions can access variables inside and outside of it 

> Ex : 

    const a = {1,2,3}
    function logger(){
        let c = "tienviet"
        console.log(c)
        console.log(a)
    }

> - The variable will access the declaration in the nearest class before using it   

> Ex : 

    { const a={1,2,3}
        {
            {
                {
                    const a = 4
                    console.log(a)
                }
            }
        }
    }

> - Life Cycle variable : 
> - + Global Variable : End Program, close file
> - + Variable in code block or function : End function, After call function, function no longer valid 