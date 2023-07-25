# TEMPERATUREconverter
This is a simple website created using HTML5,CSS &amp; JAVASCRIPT to convert the temperature.

/*HTML CODE*/

<!DOCTYPE html>

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <title>Temperature Converter</title>
    <link rel="stylesheet" href="style.css" />
    
  </head>
  <body>
   
    <div class="container">
      <h1>Temperature Converter</h1>
      <br />
      
      <select name="" id="first">
        <option value="C">Celcius</option>
        <option value="F">Fahrenheit</option>
        <option value="K">Kelvin</option>
       </select>
       
       &nbsp;&nbsp;&nbsp;&nbsp; To &nbsp;&nbsp;

      <select name="" id="second">
        <option value="C">Celcius</option>
        <option value="F">Fahrenheit</option>
        <option value="K">Kelvin</option>
      </select>

      <br />
      <br />
      <br />

      <label for="temperature">Enter the temperature : </label>
      <input type="number" name="" id="temperature" />

      <br />
      <br />
      <br />

      <input
        type="button"
        value="CONVERT"
        onclick="convert()"
        style="padding: 4px 5px; font-weight: 900"
      />

      <br />
      <br />

      <div class="result">Converted Temperature</div>
    </div>

    <script type="text/javascript" src="main.js"></script>
  </body>
</html>



//css code

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif; 
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background:url(img2.jpg)
  
}

.container {
    position: absolute;
    height: 520px;
    width: 877px;
    text-align: inherit;
    background-size: 300px 100px ;
}

//JAVASCRIPT CODE

function convert() {

    var Temperature = document.getElementById("temperature").value;
    var from = document.getElementById("first").value;
    var to = document.getElementById("second").value;
    var result = document.getElementsByClassName("result")[0];

    if (from == "C" && to == "C")
        resultString = `Celcius = ${Temperature} ℃`;

    else if (from == "C" && to == "F")
        resultString =
            "Fahrenheit = " + FromCelciusToFahrenheit(Temperature) + " ℉";

    else if (from == "C" && to == "K")
        resultString = "Kelvin = " + FromCelciusToKelvin(Temperature) + " K";

    else if (from == "F" && to == "F")
        resultString = `Fahrenheit = ${Temperature} ℉`;

    else if (from == "F" && to == "C")
        resultString =
            "Celcius = " + FromFahrenheitToCelcius(Temperature) + " ℃";

    else if (from == "F" && to == "K")
        resultString =
            "Kelvin = " + FromFahrenheitToKelvin(Temperature) + " K";

    else if (from == "K" && to == "K")
        resultString = `Kelvin = ${Temperature} K`;

    else if (from == "K" && to == "C")
        resultString = "Celcius = " + FromKelvinToCelcius(Temperature) + " ℃";

    else if (from == "K" && to == "F")
        resultString =
            "Fahrenheit = " + FromKelvinToFahrenheit(Temperature) + " ℉";

    result.innerText = resultString;
}

//   Celcius section
function FromCelciusToKelvin(Temperature) {
    var Kelvin = parseFloat(273.15) + parseInt(Temperature);
    return Kelvin;
}

function FromCelciusToFahrenheit(Temperature) {
    var Fahrenheit = (9 * parseInt(Temperature)) / 5 + 32;
    return Fahrenheit;
}

//   Fahrenheit section
function FromFahrenheitToKelvin(Temperature) {
    var Kelvin = parseFloat(273.15) + ((parseInt(Temperature) - 32) * 5) / 9;
    return Kelvin;
}

function FromFahrenheitToCelcius(Temperature) {
    var Celcius = ((parseInt(Temperature) - 32) * 5) / 9;
    return Celcius;
}

//   Kelvin section
function FromKelvinToCelcius(Temperature) {
    var Celcius = parseInt(Temperature) - parseFloat(273.15);
    return Celcius;
}

function FromKelvinToFahrenheit(Temperature) {
    var Fahrenheit =(9 * (parseFloat(Temperature) - parseFloat(273.15))) / 5 + 32;
    return Fahrenheit;
}
