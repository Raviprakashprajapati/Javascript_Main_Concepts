
### javascript was developed by Netscape and created by Brenden Eich in 1995




# Promises: It is basically a object whicih is used to handle asynchronous requests which can be resolve or reject as per condition

# Synchronous: every statement of the code gets executed one by one. Every line of code waits for its previous one to get executed first and then it gets executed.

# Asynchronous: Functions or operations that are running in parallel with the other functions or operations are called the asynchronous and it handle the taks by web API .

# Closure: A closure is simply a function inside another function that has access to the outer function variable


1. what is history of javascript ?

    JS was created by Brenden Eich in NetScape Communication in 1995. 
    Mocha -> LiveScript -> JavaScript
    JS was submitted to Ecma International , an international standards organization which provides all standards and rules for javascript and the first version of EcmaScript which is officiall standard for JS was released in 1997. 
    Gradually JS become very popular to create interractive webpages and also adapt by the internet explorer that time which was also very popular browsers at that time .
    JS become popular when Ecmascript 6 was released in whcih they provides so many modern features like classes,map,modules which help of proragmmers to write more efficient code base for javascript



2. How many ways to perform asyncrhonous taks?

    js is sinlge- threaded programming languages. this means it can only executes code line by line at a time  from top to bottom.
    BUT synchronoues exuceution can be make problem for long running tasks like if a fucntions take more time to be done which can block  the main thread of js and next code cannot be executed untill the function finished running

    To avoid this problem , js used a way to run code asynchronous.
    By using callbacks
    By using Promises
    By using Async / Await


3. How js code behing the scenes ?

    Every thing in js happens inside the EXECUTION CONTEXT where there is two parts Memory and Code part in which memory part store the variable,Funciton and code part is used to executed the code line by line.
    when js code is executed a new Execution Context created

        var n = 3; 
        function squr(num) { 
            var ans = num * num; 
            return ans; 
        } 
        var three = squr(n); 

    when code is execute 
    In Memory , for variable is reserver a special value undefined in it and for function it store whole code in it. 
    After this first line is executes then 3 value placed into the memory
    then squr(n) is executes ,and as per code function is also has a mini program in it so function will also create their owwn EXECUTION CONTEXT inside the code part/component . it also have Memory and Code part in whcih memory part store ans,num as a undefined and after allocating memory, undefined replaced by actual value in it.
    After that when return is encountered the control of program goes to place where the function is invoked and in last actual value store in it and whole excution context is deleted.




4. Tell me about Async / Await ?

    The async keyword transforms a regular JavaScript function into an asynchronous function, causing it to return a Promise.

    The await keyword is used inside an async function to pause its execution and wait for a Promise to resolve before continuing.


5. Tell me about Hoisting ?

    In Javascript, you can call a function before it is defined and you won’t get an error ‘Uncaught ReferenceError’. The reason behind this is hoisting where the Javascript interpreter always moves the variables and function declaration to the top of the current scope (function scope or global scope) before the code execution.


6. Tell me about Scope ?

    Scope is basically means accessibility of things means scope is simply a box with a boundaries for variables, func,obeject . these boundaries put restriction on these wheather we can access them or not.

    There are three ways of defined scope:
    Local Scope: allow access within the boundaries
    Global Scope: we can access aything outside the boundaries but cannot access things which inside any boundaries
    Block Scope : is everything inside the boundaries but only works for let,const and does not work for var






__Code For Above Answers__

    #Promise

    let promsie01 = new Promise((resolve,reject)=>{
        if("ravi"==="ravi"){
            resolve()
        }else{
            reject()
        }
    })

    promsie01
    .then(() => console.log("passsed"))
    .catch(() => console.log("fail"))


    #Asynch/Await

    async function display(){

    console.log("first 1")
    let promsie01 = await new Promise((resolve,reject)=>{
        setTimeout(()=>{
                console.log("promise01 2")
                resolve("promise01")
        },2000)
    }) 
    console.log("3")

    let promise02 = await new Promise((resolve,reject)=>{
        setTimeout(()=>{
                console.log("promise02 4" )
                resolve("promise02")
        },4000)
    })
    console.log("5")

    let combinedPromise = Promise.all([promsie01,promise02])
    return combinedPromise
    }

    display()
    .then((data)=>{
        console.log(data)
    })





