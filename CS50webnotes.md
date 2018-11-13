# CS50 Web Programming with Python and JavaScript


### JavaScript

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

**Query Selector**

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
