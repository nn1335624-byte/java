<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AC Remote</title>
  <link rel="stylesheet" href="./index.css">
</head>
<body>
    <script src="./index.js"></script>
    <div class="remote">
    <div class="screen">
      <p id="status">OFF</p>
      <h1 id="temp">24°C</h1>
    </div>
<button onclick="powerAC()">ON/OFF</button>
<button onclick="increaseTemp()">+</button>
<button onclick="decreaseTemp()">-</button>


</div>
</body>
</html>
body {
  background: #f2f2f2;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Arial, sans-serif;
}

.remote {
  width: 220px;
  background: #ffffff;
  border-radius: 25px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}

.screen {
  background: #d9d9d9;
  border-radius: 12px;
  padding: 15px;
  margin-bottom: 20px;
}

#status {
  font-size: 14px;
  margin: 0;
}

#temp {
  font-size: 36px;
  margin: 5px 0;
}

button {
  border: none;
  cursor: pointer;
  border-radius: 10px;
}

.power {
  width: 60px;
  height: 60px;
  font-size: 22px;
  margin-bottom: 15px;
  background: #ff4d4d;
  color: white;
}

.temp-btns button {
  width: 60px;
  height: 40px;
  font-size: 20px;
  margin: 5px;
  background: #e6e6e6;
}
let power = false;   
let temp = 24;
function powerAC() {

  if (power === false) {
    power = true;
    document.getElementById("status").innerHTML = "ON ";
  } else {
    power = false;
    document.getElementById("status").innerHTML = "OFF ";
  }

}
function increaseTemp() {

  if (power === true) {

    if (temp < 30) {
      temp = temp + 1;
      document.getElementById("temp").innerHTML = temp + "°C";
    }

  } else {
    alert(" turn on the air conditioner  ");
  }

}
function decreaseTemp() {

  if (power === true) {

    if (temp > 16) {
      temp = temp - 1;
      document.getElementById("temp").innerHTML = temp + "°C";
    }

  } else {
    alert(" turn on the air conditioner ");
  }

}
