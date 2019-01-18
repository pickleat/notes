# Node JS 8 The Right Way by Jim R. Wilson

## Chapter 1 - Getting Started

- Thinking Beyond The Web
    - Lovely little map that shows the landscape of Node.JS. On the Left you have "Server Side"; which includes: messaging, IPC, monitoring, tests, and builds, and distribution. Included in this is the "web" which is made up of REST, Ajax, and HTTP. On the right side you have the "Client Side" which is made up of GUI, web apps and mobile apps. Client-Side apps interact with humans.
- Node.js's Niche
    - JavaScript first appeared in 1995, and has been solving problems along the front/back end spectrum ever since. 
    - JS' use bookends that of Node.js. From Databases to the GUIs.
    - Node.js specifically deals with middleware, APIs, Web Services, Robotics, and IoT.
- How Node.js Apps work:
    - JS + *event loop*
    - You load your program and it waits for something to happen, it executes any callbacks and then checks if there is anything more to do. It repeats this process until there is nothing left to do, at which time it exits.
    - As long as there is something left to do, the *event loop* will keep on spinning.
    - The job of a Node.js dev is to do create callback functions that get executed in response to events.
- Single Threaded and Highly Parallel
    - Node.js is single-threaded, meaning only one line of code is running at a time.
    - It gets away with this by using *callback functions*. Which is invoked when another operation passes/fails.
- Aspects of Node.js Development
    - 5 Things in Particular
        1. Practical Programming: Real code that does something useful
        2. Node.js Core: Event loop is in see, but executes in JavaScript
        3. Patterns: Node.js has lots of repeating patterns, some baked in, others are from external libraries. But recognizing patterns is important.
        4. JavaScript-isms: uses JS lang, like arrow functions, spread parms/operators
        5. Supporting Code: it takes a village and using supporting code (like testing packages) helps make all code better.

## Chapter 2 - Wrangling the File System

- Intro
    *- Node.JS Core*: from an architecture front, you'll start to see how the event loop shapes a program's flow. We'll use *buffers* for transporting data between Node.js's JS engine and its native core. We'll use the node.js module system to bring in libraries.
    - *Patterns*: common ones include callbacks for aysnchronus events. We'll use ```EventEmitter``` and ```Stream``` classes to pipe data.
    - *JavaScriptisms*: features and best-practices.
    - *Supporting Code*: how to spawn and interact with child processes. Capture and detect state changes.
- Programming for the Node.js *Event Loop*
    ```js
    'use strict';
    const fs = require('fs');
    fs.watch('target.txt', () => console.log('file changed'));
    console.log('now watching for file changes on target.txt');
    ```
    - ```'use strict'``` this disables some problematic JS features, and throws some useful errors.
    - ```const``` is a variable declaration that must be assigned a value and that value cannot changed. aka a *constant*
    - ```require()``` pulls in the Node module and returns it. ```'fs'``` is just nodes built in filesystem module.
    - ```watch()``` is a method of the ```fs``` module which takes a path to the file and a callback function whenever the file changes.
    - *A note about functions*: in JS functions are first-citizens. They can be assigned to variables and passed as parameters to other functions.
    - ```() => console.log('file changed')``` the first empty parentheses is just saying that the arrow function doesn't expect any arguments. The body, just prints the statement in the console.
        - in the past you would've declared this arrow function like this, much longer.
        ```js
        function() {
            console.log('file changed');
        }
        ```
    - Arrow functions take away the confusion of using ```this``` because they don't create a new scope for ```this```. These should be your go-to declarations for callbacks.
- Visualizing the Event Loop: here's what Node.js does:
    - Loads the script, running all the way through the code, which produces the "now watching..." message
    - It sees there is more to do because of the ```fs.watch()```
    - It waits for something to happen, specifically for the file to change
    - It executes the callback function when the file changes
    - It determines the program isn't finished and resumes waiting.
- Reading Command-Line Arguments
    - Let's write a new file, very similar to the previous example:
    ``` js
    const fs = require('fs');
    const filename = process.argv[2];
    if (!filename) {
        throw Error('You must specify a file to watch');
    }
    fs.watch(filename, () => console.log(`File ${filename} has changed!`));
    console.log(`Now watching ${filename} for changes...`);
    ```
    - This file functionally does much the same as the previous, but it adds a second command-line argument of a file to watch, whereas the first only watched a file called target.txt. Now any file can be watched.
    - Note: the backticks "`" are very important. These are called *template strings* and they allow you to place an expression inside a string so that it will insert the variable with the stringified result.
- Spawning a Child Process
    - The point here is to spawn a *child process* in response to changes and how to use streams to pipe around data.
    ``` js
    'use strict';
    const fs = require('fs');
    const spawn = require('child_process').spawn;
    const filename = process.argv[2];

    if (!filename) {
        throw Error('A file must be specified');
    }
    fs.watch(filename, () => {
        const ls = spawn('ls', ['-l', '-h', filename]);
        ls.stdout.pipe(process.stdout);
    });
    console.log(`now watching ${filename} for changes...`);
    ```
    - This file, much like the previous examples uses a new ```require('child_process').spawn;``` statement. This built in module, uses a specific ```spawn()``` method. Because we only care about the spawn method specifically, we bound it to the spawn variable, and ignored the rest of the module.
    - Look at the callback function passed to ```fs.watch()```, 
        - It is different from the previous callbacks in that it is a multi-line declaration.
        - The first parameter to ```spawn()``` is the filename ```'ls'```. The second parameter is the array of command-line arguments, including the flag of the filename we are watching.
        - The object returned is a *ChildProcess*. Its *stdin*, *stdout*, and *stderr* properties are *streams* that can be used to read and write data.
        - The ```pipe()``` method sends the standard output from the child process directly to our stream.
- Capturing Data from and EventEmitter.