🔥 React JS 🔥

🌟 Advanced JS topics for React ✅

1. ES5 vs ES6
2. Array, objects, functions
3. Arrow functions/Normal Functions
4. Array methods (map, filter, reduce, find, findIndex)
5. Destructuring
6. Rest Spread
7. try catch
8. async await
9. promises

<hr style= "border-top: 1px dotted #ccc;">

🌟 Starting with React.js ✅

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 Install Node.js

🔗 https://nodejs.org/en

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 create-next-app (React folder description)

🪜 Step 1: Open terminal\
🪜 Step 2: Write

            npx create-next-app

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 UseState Hook (Variable of react ) and Real DOM and Virtual DOM ✅

-->

🌟 Real DOM

📌 Real DOM is the actual structure of the webpage.\
📌 React Update complete document in the Real DOM.\
📌 React DOM is the actual webpage rendered on the browser any changes made\
 directly reflect on the complete webpage.\
📌 The DOM represents the web page often called a document with a logical\
 tree and each branch of the tree ends in a node and each node contains objects. \
📌 The developer can modify the content of the document using a scripting language like JavaScript.\
📌 The changes and updates to the DOM are fast because of its tree-like\
 structure but re-rendering whole documents makes the DOM slow.\
📌 All UI components need to be re-rendered for every DOM update.

![Real DOM Tree](https://media.geeksforgeeks.org/wp-content/uploads/20220905155609/RealDOM-660x330.jpg)

🌟 Virtual DOM

📌 Virtual DOM is the virtual represenation of Real DOM\
📌 React update the state changes in Virtual DOM first and then it syncs with Real DOM\
📌 Virtual DOM is just like a blueprint of a machine, can do changes in the\
 blueprint but those changes will not directly apply to the machine.\
📌 Virtual DOM is a programming concept where a virtual representation of a\
 UI is kept in memory synced with "Real DOM" by a library such as ReactDOM\
 and this process is called reconciliation.\
📌 Virtual DOM makes the performance faster, not because the processing\
 itself is done in less time. The reason is the amount of changed \
 information - rather than wasting time on updating the entire page,\
 you can dissect it into small elements and interactions.

![Virtual DOM Tree](https://media.geeksforgeeks.org/wp-content/uploads/20220905155609/VirualDOM-660x330.jpg)

🌟 Differences between Real Dom and Virtual Dom

| Real DOM                            | Virtual DOM                          |
| :---------------------------------- | :----------------------------------- |
| Real DOM represent actual structure | Virtual DOM represent the            |
| of the webpage.                     | virtual/memory representation of     |
|                                     | the Webpage.                         |
|                                     |                                      |
| DOM manipulation is very expensive  | DOM manipulation is very easy        |
|                                     |                                      |
| There is too much memory wastage    | No memory wastage                    |
|                                     |                                      |
| It updates Slow                     | It updates fast                      |
|                                     |                                      |
| It can directly update HTML         | It can't update HTML directly        |
|                                     |                                      |
| Creates a new DOM if the element    | Update the JSX if the element update |
| updates.                            |                                      |
|                                     |                                      |
| It allows us to directly target     | It can produce about 200,000 Virtual |
| any specific node (HTML element)    | DOM Nodes / Second.                  |
|                                     |                                      |
| It represents the Ul of your        | It is only a virtual representation  |
| application                         | of the DOM                           |
|                                     |                                      |

🌟 useState hook is used to create variable in react.

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 calling functions in react (Functions)

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 Two Way binding ✅

--> Suppose there is a form and you want to give input to it, in that case\
you have to first create a variable using the useState hook and then set the value \
of the input to the variable and then inside an onClick function you have to change the\
events using set function.

⭐Exmp:

        "use client";

        import React, { useState } from "react";

        const Home = () => {
          const [username, setUsername] = useState("");

          return (
            <>
              <h1 className="ml-5 mb-5 text-2xl">Enter your name</h1>
              <form action="">
                <input
                  className="ml-5 border-2 border-zinc-800 px-4 py-2 text-xl"
                  type="text"
                  value={username}
                  onChange={(e) => {
                    setUsername(e.target.value);
                    console.log(username);
                  }}
                />
              </form>
            </>
          );
        };

        export default Home;

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 Routing, Dynamic Routing

--> Routing is normal like you have to create a folder in name of your route let say\
Contact and then create a page.jsx inside it. You can also create a layout.jsx if required.\

🌟 Dynamic Routing

--> Create a folder with brackets [<|name|>] and it will be your dynamic routing

⭐Exmp: 

![Real DOM Tree](./Screenshot%202024-01-15%20142834.png)

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 ToDo app

## 🎯 Breaking the components (importance of components) ✅

## 🎯 props (normal data, children) ✅

## 🎯 Introduction to class components (via lifecycle method) \*not imp

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 useEffect lifecycle hook ✅

--> useEffect is basically used for running any code or function by itself

⭐Exmp: 

    const [users, setUsers] = useState([]);

    const getUsers = async () => {
    let { data } = await axios.get(
      "https://jsonplaceholder.typicode.com/users"
    );
    setUsers(data);
    }


    useEffect(() => {
      getUsers();
    }, []);

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 API calling (fetch API / Axios) ✅

--> 

⭐Exmp: 

        "use client";

        import axios from "axios";
        import Link from "next/link";
        import React, { useEffect, useState } from "react";

        const Home = () => {
          const [users, setUsers] = useState([]);

          const getUsers = async () => {
            let { data } = await axios.get(
              "https://jsonplaceholder.typicode.com/users"
            );
            setUsers(data);
          };

          useEffect(() => {
            getUsers();
          }, []);

          return (
            <div>
              <button
                onClick={getUsers}
                className="bg-green-500 text-white px-4 py-2 rounded font-bold"
              >
                Get Data
              </button>
              <div className="w-full p-8 bg-slate-200 mt-5">
                <ul>
                  {users.map((e, id) => {
                    return (
                      <li key={id}>
                        {e.username} --- <Link href={`/${e.id}`}>Explore</Link>
                      </li>
                    );
                  })}
                </ul>
              </div>
            </div>
          );
        };

        export default Home;

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 Showing flash message (react toastify) ✅

--> Go to 🔗 https://fkhadra.github.io/react-toastify/introduction

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 context api (higher order components {HOC}, higher order functions {HOF}) ✅

--> 🌟Context API - It provides a way to pass data through the component tree without having\
to pass props down manually at every level.

In typical React app, data is passed top-dwon (parent to child) via props, but such usage can\
be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required\
by many components within an app. Context provides a way to share values like these between\
components without having to explicitly pass a prop through every level of the tree.

Create a folder outside and then create the 'Context.jsx' file

There are functions like 

🌟 createContext

    const SomeContext = createContext(defaultValue)

📌 Refer to this link for better understanding

🔗 https://react.dev/reference/react/createContext

<hr style= "border-top: 1px dotted #ccc;">

## 🎯 cashbook app

## Deployment via Netlify