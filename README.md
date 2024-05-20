## Task - 1
#### 1. Object comparison 
   - Here's a JavaScript program that accomplishes the task you've described. The program creates two objects, compares their properties, and checks if they are equal.
```javascript
Copy code
// Define the first object with properties
let obj1 = {
    prop1: "value1",
    prop2: "value2"
};

// Define the second object with properties
let obj2 = {
    prop1: "value1",
    prop2: "value2"
};

// Function to compare two objects
function compareObjects(obj1, obj2) {
    for (let key in obj1) {
        if (obj1[key] !== obj2[key]) {
            return false;
        }
    }
    return true;
}

// Run the comparison and store the result
let areEqual = compareObjects(obj1, obj2);

// Output the result
if (areEqual) {
    console.log("The objects are equal.");
} else {
    console.log("The objects are not equal.");
}
```
### Explanation:
 1. Object Definitions:
     - obj1 and obj2 are defined with properties prop1 and prop2.

 2. Comparison Function:
     - The compareObjects function takes two objects as arguments.
     - It loops through each key in obj1 and compares its value with the corresponding key in obj2.
     - If any value doesn't match, it returns false.
     - If all values match, it returns true.
 3. Comparison and Output:
     - The comparison result is stored in the areEqual variable.
     - An if statement is used to print whether the objects are equal or not.
     - This code will run successfully and output whether the two objects are equal based on their properties.

## Task - 2
#### 2. Display all the country flags in the console.<br>
 - The XMLHttpRequest in JavaScript to fetch data from a given URL, parse the JSON response, and log all country flags to the console. Below is the code you can use in VS Code.
 - Open VS Code and create a new file called index.html.
 - Paste the following HTML and JavaScript code into the file.
 - Replace the URL_HERE placeholder with the actual URL from which you want to fetch the data.
 - Open the index.html file in a web browser to see the output in the console.
 - Here's the complete code:
``` html
html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Country Flags</title>
</head>
<body>
    <script>
        // Create a new XMLHttpRequest object
        var xhr = new XMLHttpRequest();

        // Configure it: GET-request for the URL
        xhr.open('GET', 'URL_HERE', true);

        // Send the request over the network
        xhr.send();

        // This will be called after the response is received
        xhr.onload = function() {
            if (xhr.status != 200) { // analyze HTTP response status
                console.error(`Error ${xhr.status}: ${xhr.statusText}`); // e.g. 404: Not Found
            } else {
                // Show the result
                // Response is ready and JSON parsed
                var countryArr = JSON.parse(xhr.responseText);

                // Loop through the array of countries and log the flag URLs
                for (var country of countryArr) {
                    console.log(country.flags);
                }
            }
        };

        xhr.onerror = function() {
            console.error('Request failed');
        };
    </script>
</body>
</html>
```
 - Replace URL_HERE with the actual URL that returns the JSON data. For example, if the URL is https://example.com/countries, your xhr.open line will look like this:

```javascript
        xhr.open('GET', 'https://example.com/countries', true);
```
 - After you replace the URL and open the index.html file in a browser, you should see the URLs of all country flags logged in the browser's console.

## Task - 3
#### 3. Display the all country name, regions, sub-regions population 
 - Here is the step-by-step code to achieve the desired functionality using XMLHttpRequest:
 - Create a new XMLHttpRequest.
 - Change the default URL to the given link.
 - Parse the response as JSON.
 - Use a for...of loop to log the desired properties of each country.
 - Below is the complete code. Copy and paste this into a file in VS Code and run it to see the output.

```javascript
Copy code
// Step 1: Create a new XMLHttpRequest
var xhr = new XMLHttpRequest();

// Step 2: Open a connection to the given URL
xhr.open("GET", "https://restcountries.com/v3.1/all", true);

// Step 3: Set up a function to handle the response
xhr.onload = function () {
    if (xhr.status == 200) {
        // Step 4: Parse the JSON response
        var countryArr = JSON.parse(xhr.responseText);

        // Step 5: Use a for...of loop to log country details
        for (var country of countryArr) {
            console.log(country.name.common);
            console.log(country.region);
            console.log(country.subregion);
            console.log(country.population);
            console.log(country.flags.png);
        }
    }
};

// Step 6: Send the request
xhr.send();
```
#### Explanation:

 - The XMLHttpRequest object xhr is created.
 - The open method initializes a request to the provided URL (https://restcountries.com/v3.1/all).
 - The onload event handler is set up to process the response once it's loaded.
 - Inside the onload function, if the request status is 200 (OK), the response is parsed as JSON and stored in the variable countryArr.
 - A for...of loop iterates over each country in countryArr, logging the common name, region, subregion, population, and flag URL (PNG format) of each country.
 - The send method sends the request.
 - To run this code, ensure you have a local server set up if running this in a browser, as many browsers block XMLHttpRequest requests from local files for security reasons. Alternatively, you can use tools like Live Server in VS Code.









