# JavaScript DOM Crash Course

## [Part-1](https://www.youtube.com/watch?v=0ik6X4DJKCc&list=PLillGF-RfqbYE6Ik_EuXA2iZFcE082B3s)

> Code for the video [Download](https://www.youtube.com/redirect?q=http%3A%2F%2Fwww.traversymedia.com%2Fdownloads%2Fdomcrashcourse1.zip&redir_token=C1hY8c7caGA0J903SClpt5YZstR8MTU0MzM2ODAwNEAxNTQzMjgxNjA0&event=video_description&v=0ik6X4DJKCc)

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
            - stopped video at 27:11