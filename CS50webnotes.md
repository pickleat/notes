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