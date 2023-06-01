# Projects-of-bharatIntern
Simple web Temperature Convertor


<!DOCTYPE html>
<html>
<head>
  <title>Temperature Converter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 100px;
    }
    
    h1 {
        color: rgb(228, 95, 199);
    }
    
    .form-group {
      margin-bottom: 20px;
    }
    
    label {
      display:  inline-block;
      width: 120px;
      text-align: right;
    }
    
    input[type="text"] {
      padding: 5px;
      width: 200px;
    }
    
    #result {
      font-weight: bold;
      margin-top: 20px;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      margin-top: 50px;
    }
    
    .form-container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
    }
    
    .form-group {
      margin-bottom: 20px;
    }
    
    label {
      /* display: inline-block; */
      width: 120px;
      text-align: right;
      margin-right: 10px;
    }
    
    select,
    input[type="text"] {
      padding: 9px;
      border: 1px solid rgb(141, 116, 233);
      border-radius: 3px;
    }
    
    input[type="submit"] {
      padding: 12px 150px;
      background-color: #867ed8;
      color: #fff;
      border: none;
      border-radius: 20px;
      cursor: pointer;
    }
    
    #result {
      color: #6060d1; 
      font-weight: bold;
      margin-top: 50px;
      font-size: 22px;
    }
  </style>
</head>
<body style="background-color:rgb(204, 234, 235);">
   
  <h1>Temperature Converter</h1>
  <div class="container">
    <div class="form-container">
      <div class="form-group">
        <label>Temperature:</label>
        <input type="text" id="temperature" placeholder="Enter temperature" />
      </div>
      <div class="form-group">
        <label>From: </label>
        <select id="fromUnit">
          <option value="celsius">Celsius</option>
          <option value="fahrenheit">Fahrenheit</option>
          <option value="kelvin">Kelvin</option>
        </select>
      </div>
      <div class="form-group">
        <label>To: </label>
        <select id="toUnit">
          <option value="celsius">Celsius</option>
          <option value="fahrenheit">Fahrenheit</option>
          <option value="kelvin">Kelvin</option>
        </select>
      </div>
      <input type="submit" value="Convert" onclick="convertTemperature()" />
    </div>
    <div id="result"></div>
  </div>
  
  <script>
    function convertTemperature() {
      var temperature = parseFloat(document.getElementById("temperature").value);
      var fromUnit = document.getElementById("fromUnit").value;
      var toUnit = document.getElementById("toUnit").value;
      
      var convertedTemperature;
      
      if (fromUnit === "celsius") {
        if (toUnit === "fahrenheit") {
          convertedTemperature = (temperature * 9/5) + 32;
        } else if (toUnit === "kelvin") {
          convertedTemperature = temperature + 273.15;
        } else {
          convertedTemperature = temperature;
        }
      } else if (fromUnit === "fahrenheit") {
        if (toUnit === "celsius") {
          convertedTemperature = (temperature - 32) * 5/9;
        } else if (toUnit === "kelvin") {
          convertedTemperature = (temperature - 32) * 5/9 + 273.15;
        } else {
          convertedTemperature = temperature;
        }
      } else if (fromUnit === "kelvin") {
        if (toUnit === "celsius") {
          convertedTemperature = temperature - 273.15;
        } else if (toUnit === "fahrenheit") {
          convertedTemperature = (temperature - 273.15) * 9/5 + 32;
        } else {
          convertedTemperature = temperature;
        }
      }
      
      document.getElementById("result").innerHTML =  "Result: " +convertedTemperature.toFixed(1) + " " + toUnit;
    }
  </script>
</body>
</html>
