# react-project

Notes:

review the javascript basics:

1.Destructuring

2.restspread operator ... ;
#used to combine or update the array or object.
#the spread of original object should be put first.

3.Template Literals
#combine text and varialbe. `${variable or js expression} + text`;

4.Ternaries instead if/else;

5.Arrow functions
#quick easy way to write one line function.
#if use curly brace, need add return;

6. Short-circuiting and logical operators: $$,||,??
   #the first is true, then print the second
   console.log("hello" && "string"); string
   console.log(0 && "string"); 0

   #the first is false, print the second one
   console.log(true || "string"); true
   console.log(false || "string"); string

   #similar with ||, the ?? only return the second one if the first is null or undifined, so 0 and empty stirng do not work here.
   console.log(true || "string"); true
   console.log(false || "string"); string

7.optional chaining
#put a ? in the chain to prevent not found error.
example: const librarything = book.reviews.librarything?.reviewsCount;
check the part before ?

8.Array method: Map method
#Array.map((el)=>{return }) for each element of this array, do sth..
#return a array.

9.Array method: filter method
#const filteredArray = array.filter((item)=>item.property>100);
#retrun a array that satisfied the condition

10.Array Reduce method
#perform calculations reduce(fn,init value)
#const pagesAllBooks = books.reduce((acc,book)=>acc+book.pages,0)
#it could be complex because the init value can be array ,obeject.

11.Array Sort method
#arr.sort((a,b)=>a-b); ascending order
#arr.sort((a,b)=>b-a); descending order
#it will change the original array, so we do not need to assign it to a new array.
#arr.slice().sort((a,b)=>a-b) we could use sliec() to copy the array to avoid change it.
#const sortedByPages = books.slice().sort((a,b)=>b.pages - a.pages);

12. working with immutable arrays
    //add book object to array
    const newBook={
    id:6,
    title:"Harry Potter",
    author:"J.K. Rowling",
    };

const booksAfterAdd = [...books, newBook];

//delete book object from array
const bookAfterDelete = booksAfterAdd.filter((book) => book.id !== 3);

//update book object in the array
const booksAfterUpdate = booksAfterDelete.map((book)=>book.id === 1 ? {...book, pages:1}: book);

13.asynchronous javascript: promise
#fetch(api) will return a promise, so we could apply then method on it.
fetch("https://jsonplaceholder.typicode.com/todos")
.then(res=>res.json()) //returns a promise
.then(data=>console.log(data)); //returns a promise, so use then again

14.asynchronous javascript: Async/Await
async function getTodos(){
const res = await fetch("https://jsonplaceholder.typicode.com/todos");
const data = await res.json();
console.log(data);
}

-----debugging methods------

1. make sure the application is running.
2. see message in problems tabs or inspect browser.

----component---
including: data,logic appearance

-----jsx------
1.describe what components look like and how they work

#JSX is Declarative (not Imperative), it describes what UI look like using JSX, based on current data. Not do things step by step!
#never touch DOM

2. must return a block of jsx

3.extension of js that allows us to embed js,css,react components

4. a tool called BABEL transfer jsx to javascript.

5. we could use React without JSX.
