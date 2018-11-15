# Data Visualization Certification Notes

## Data Visualization with D3

## JSON APIs and Ajax

### Introduction
* APIs: Application Programming Interfaces help programs interact with others. APIs are just tools that computers use to exchange data.
* AJAX: Short for Asynchronous JavaScript and XML. It refers to technologies that make requests to transfer data and do so in an asynchronous way. Asynchronous meaning, the browser does not wait for that portion to load in order to move on with the page. Which is better for UX. They may have a blank portion until its done, but they can interact other places on the page while they wait. 
* JSON. Most often the data transfer comes in the form of a JavaScript Object Notation. JSON looks like JavaScript Object, but comes enclosed in strings and must be converted back to an object before it can be used effectively. 

### Lessons
* You want to make sure you don't run the code until the page has loaded, so you added an **event** to the document called ``` DOMContentLoaded``` like so:
``` html
document.addEventListener('DOMContentLoaded',function() {
});
```
you can also add a **handler** that triggers based on the handler's type. like `onclick` here's a quick example: ```document.getElementById('getMessage').onclick=function(){};```
* From there you can add even more by inserting further instructions inside the brackets of the above code. This example, takes the code associated with the class and inserts new content with: ```document.getElementsByClassName('message')[0].textContent="Here is the message";```
* Requesting from another source:
    * Most APIs send data as a JSON, which is much like a JavaScript Object, but instead it sent as bytes, and recieved as a ```string```, so you uses the ```JSON.parse``` method to parses it into an object. 
    * using our same example you can request a JSON inside a click event with the ```XMLHttpRequest``` object. Here's an example:
```
req=new XMLHttpRequest();
req.open("GET",'/json/cats.json',true);
req.send();
req.onload=function(){
  json=JSON.parse(req.responseText);
  document.getElementsByClassName('message')[0].innerHTML=JSON.stringify(json);
};
```
* what is each piece doing? 
    * first ```req``` is making a request and storing it in a variable
        * its arguments ```GET``` is the type of request, ```'/json/cats.json'``` is URL of the API, ```true``` makes the request asynchronously. 
    * ```req.send()``` is sending the request
    * ```req.onload``` is an event handler that parsing the returned information into a readable object and then inserts it into the message text. 
#### Accessing JSON data from an API
* Refresher on JS Notation ```[ ] -> Square brackets represent an array
    { } -> Curly brackets represent an object
    " " -> Double quotes represent a string. They are also used for key names in JSON```
* If you know how the JSON is formed you can index into the object with either bracket [] or dot notation '.'
* If you need to parse through all of it you can use the ```forEach``` method and then input the items into the html directly like so:
``` html 
json.forEach(function(val) {
  var keys = Object.keys(val);
  html += "<div class = 'cat'>";
  keys.forEach(function(key) {
    html += "<strong>" + key + "</strong>: " + val[key] + "<br>";
  });
  html += "</div><br>";
});
```

* Another example that embeded images using the ```forEach``` method
* Prefilter JSON to the the Data you need
    * use the ```filter``` method to filter out or in specific items. Like so: ```json = json.filter(function(val) { return (val.id !== 1);
});```

#### Get Geolocation Data
```html
<script>
  if (navigator.geolocation){
  navigator.geolocation.getCurrentPosition(function(position) {
    document.getElementById('data').innerHTML="latitude: "+ position.coords.latitude + "<br>longitude: " + position.coords.longitude;
  });
}
</script>
<h4>You are here:</h4>
<div id="data"></div>
```

#### Post Data with the XMLHttpRequest Method
* This was really unclear to me. 🤷🏻‍♂️