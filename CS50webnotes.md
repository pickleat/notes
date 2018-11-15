# CS50 Web Programming with Python and JavaScript


## JavaScript

``` html
<script>
function hello() {
    alert(“hey there”);
}
</script>

<!-- later -->

<button onclick=”hello()”>Click Here!</button>
```

``` html
<script>
function hello() {
    document.querySelector('h1').innerHTML = 'Goodbye';
}
</script>
```

### **Event Selectors**

* onclick (when it is clicked)
* onmouseover (when it is
* onkeydown (when a key is pushed down)
* onkeyup (when a key comes back up)
* onload (when something is loaded)
* onblur
* onsubmit


### **Query Selector**

* document.querySelector('tag')
* document.querySelector('#id')
* document.querySelector('.class')

``` html
<html>
    <head>
        <script>
            let counter = 0

            function count() {
                counter++; 
                document.querySelector('#counter').innerHTML = counter;
            }
        </script>
        <title> A Website </title>
    </head>

    <body>

    </body>
</html>

```

You can add javascript outside much like a css doc like so:

``` html
<head>
<script src="nameoffile.js"></script>
</head>
```

### **Variables**

* const: stands for 'constant' when declared can't change
* let: only exists inside the innermost set of curly braces
* var: can be hoisted outside of the curly braces (i think)

### Arrow Functions

``` js
() => {
    alert('Hello World');
}
```

You can remove function name, then move on to what the code does. 

### this.

* **this.** is a keyword that refers to whatever value is being operated upon.
  * only bound to the function when it is

### JavaScript/HTML

* you can change any HTML property with javascript above it in the ```<script>``` as long as it's valid code.
* 


### Local Storage

* localStorage is a variable that allows you to save a state or information. Most modern web browsers support this. <-- Brian mentions that this will be usesful in the future
    * how is this different than a cookie? Local storage is completely local to the user, but a cookie is involved with a server somewhere. 

### AJAX

* Async JavaScript and XML
* AJAX allows you to make a request without having to use ALL the information it might use. Example: currency exchange. He types in a currency and it returns a message of the current exchange rate. This utilizes an AJAX request that allows the webpage to only get the information it NEEDS instead of downloading all the exhchange rates (more download) and dipslaying only the one the user wants.

### Socket.IO

* You don't always want to refresh your page to make a request to see any new messages.
* Web Sockets are a way to look for live information and keep updating in real time.
* in application.py use the header to access socket **from flask_socketio import SocketIO, emit**

    * "emit" allows you to broadcast and event to the server with the data you've sent.
    * in application.py you then have a new route, written like this: 

    ``` python
    @socketio.on("submit vote")
    def vote(data):
        selection = data["selection"]
        emit("announce vote", ) #... not finished
    ```

    * then back in your javascript, you'll create a function that accepts the "announce vote" event and run a function that updates the app with the data sent.