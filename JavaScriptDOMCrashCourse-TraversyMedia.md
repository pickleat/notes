# JavaScript DOM Crash Course

## [Part 1](https://www.youtube.com/watch?v=0ik6X4DJKCc&list=PLillGF-RfqbYE6Ik_EuXA2iZFcE082B3s)

> Code for the video [Download](https://www.youtube.com/redirect?q=http%3A%2F%2Fwww.traversymedia.com%2Fdownloads%2Fdomcrashcourse1.zip&redir_token=C1hY8c7caGA0J903SClpt5YZstR8MTU0MzM2ODAwNEAxNTQzMjgxNjA0&event=video_description&v=0ik6X4DJKCc)

> Note before. He doesn't ever mention where to put the link to your JavaScript doc. It must be BELOW everything at the bottom of the page, otherwise, the javascript will run BEFORE it actually sees any of the elements and return ```null```. So before you close the final ```</html>``` add your ```<script src="fileName.js"></script>``` so your javascript will work correctly. 

- What is the DOM?
    - Document Object Model
    - Tree of nodes/elements created by the browser
    - JavaScript can be used to read/write/manipulate the DOM
    - **Object Oriented**
    - The DOM 'tree' follows the hierarchy of the html doc it is apart of.

- ```console.dir(document);```
    - this will show you all of the information that is in the document. Tags, elements, etc...
    - These items are editable and available for reassignment. So if you said ```document.title = 123;``` it would change the ```title``` to the number 123.
    
- Selectors
    - ```Document.getElementById(titleName)``` gets the id with the name ```titleName``` you can use it to reassign the variable
    - ```.textContent``` and ```.innerText``` are two ways to change the content of a element that has been selected. For example if you assign some text like so:
        - ```titleName.textContent = 'Hello';```  
        - ```titleName.innerText = 'Goodbye';```
        - the difference between the two is that ```.textContent``` disregards styling, and ```.innerText``` pays attention to styling.
    - ```.innerHTML``` this inserts another html element into an existing method.
    - Changing Styles
        - you have to use camelCase instead of dashes (-) even if they style includes a dash.
    - ```Document.getElementsByClassName()``` if there are multiple items you recieve an HTMLCollection, which can be indexed, or assigned to a variable and then altered. like so:
        - ```var items = Document.getElementsByClassName(someClass);```
            - You can alter with the same methods as before, but in order to go through and change every item with a particular class, you need a ```for``` loop like so:
            ``` js
            for(var i = 0; i < items.length; i++) {
                items[i].style.backgroundColor = '#f4f4f4';
            }
            ```
            - this would go through and find every element with class name of ```someClass``` that is found in the variable ```items``` and change its style to have the background color of #f4f4f4.
            - ```getElementsByTagName(tagName)``` here you'd use the tag name like ```li``` or ```h2```. It works similarly to ```.getElementsByClassName```, just utilizes the ```tag``` instead.
    - ```.QuerySelector()```
        - Allow you to select a single/first item with whatever parameter you put in the parens. It could be an ID like ```#main-header``` or a class, really anything.
        - If you want all items of that type, use ```.QuerySelectorAll()```
            - if there are more items, it will return a NodeList which works like a collection.
        - From either of these selectors you can use css pseudo classes like ```'li:nth-child(odd)'``` and then a ```for``` loop to alter the style. 

## [Part 2](https://www.youtube.com/watch?v=mPd2aJXCZ2g&index=2&list=PLillGF-RfqbYE6Ik_EuXA2iZFcE082B3s)

> Code for this [Video](https://www.youtube.com/redirect?event=video_description&v=mPd2aJXCZ2g&q=http%3A%2F%2Fwww.traversymedia.com%2Fdownloads%2Fdomcrashcourse2.zip&redir_token=5GMUfgEhgBpl1c7DnK4435FiN6h8MTU0MzQyMDg0NUAxNTQzMzM0NDQ1)

- Traversing the DOM
    - Looking at parent, child, and sibling nodes. This works how you would expect.
    ``` html
        <div> <!-- Parent -->
            <h2> <!-- Child of <div> --> </h2>
            <p> <!-- Child of <div>; Sibling of <h2> -->
                <li> <!-- Child of <p>; Grandchild of <div> --> </li>
                <li> <!-- Child of <p>; Grandchild of <div> --> </li>
            </p>
        </div>
    ```
    - Parent Nodes
        - if you have already selected something like a class of ```#items``` with a variable, you can then access it's parentNode like so: ```varName.parentNode.style.backgroundColor = '#f3f3f3';``` to change its background color or any other style. ```.parentNode``` can be changed together to continue to go up the family tree of the DOM.
        - ```parentElement``` can be used similarly
    - Child Nodes
        - If you use ```varName.childNodes```you'll recieve a NodeList if there is more than one. It can be a bit of a pain, because it will return EVERY child item, including all line breaks. Which can be tedious. 
        - Instead use ```varName.children``` will return an ```HTMLCollection``` which can be indexed for a specific item in the collection. 
        - ```firstChild``` returns whatever the first child is, which can give you a line break instead ```firstElementChild``` will respond with the first element which is more likely to be useful.
        - ```lastChild``` and ```lastElementChild``` also exist.
    - Siblings
        - ```nextSibling``` will return whatever the next node is, sometimes unhelpful. 
        - ```nextElementSibling``` will return the next. 
        - ```previousSibling``` and ```previousElementSibling``` also exist.
- Creating/Inserting Elements
    - ```createElement('elementType')``` you can use any tag like ```div```
    ``` js
        var newDiv = document.createElement('div');
        newDiv.className = "hello";
        newDiv.id = 'hello1';
        newDiv.setAttribute('title', 'Hello Div');
        var newDivText = document.createTextNode('Hello World');
        newDiv.appendChild(newDivText);
        var container = document.querySelector('header .container'); // these are just classes in the example html
        var h1 = document.querySelector('header h1'); // more common, but these exist in the html doc in the example
        container.insertBefore(newDiv, h1); // uses the var 'container' and the method 'insertBefore()' which takes 2 params to insert the new div, with the var h1.
    ```

### [Part 3](https://www.youtube.com/watch?v=wK2cBMcDTss&list=PLillGF-RfqbYE6Ik_EuXA2iZFcE082B3s&index=3)
> Code for this [Video](https://www.youtube.com/redirect?redir_token=WWyqJgFlo5eAajTvh8FewRCzao98MTU0MzQyMjg2N0AxNTQzMzM2NDY3&q=http%3A%2F%2Fwww.traversymedia.com%2Fdownloads%2Fdomcrashcourse3.zip&event=video_description&v=wK2cBMcDTss)

- Events / Listeners
    - Old way: inline HTML
    ``` html
    <button class="btn btn dark" onclick="alert(1)" id="button">Click Here</button>
    ```
    - Better Way: use and ```eventListener``` to keep JS separate. 
    ``` js
        var button = document.getElementById('button').addEventListener('click', function(){
            console.log(123);
        });
    ```
    - you can also add parameters and then index to retrieve more information or create specific things. like:
    ``` js
    document.getElementById('button').addEventListener('click', function(e){
    console.log(e); // where e is just an argument that will output all the things associated with the click event.
    });
    ```    
    - you could put in a specific item for if a key is pressed with the click. like ```console.log(e.altKey);``` would return true or false to see if the key is being pressed when the button is clicked. This could be useful to add functionality.

- Types of events ```var.addEventListener('eventType', 'functionName');```
    - ```click``` / ```dblclick```
    - ```mousedown``` / ```mouseup```
    - ```mouseenter```/ ```mouseleave```
    - ```mouseover``` / ```mouseout``` Slightly different than above, but similar
    - ```mousemove``` any time a mouse is moving inside the selected element.
    - stopped at 19:53