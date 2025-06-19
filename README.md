<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Calorie Count by A</title>
  <style>
    body {
      background-color: #000;
      color: #fff;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 40px;
    }

    h1 {
      color: #00ffcc;
    }

    .form-group {
      margin: 20px auto;
      width: 300px;
    }

    label {
      display: block;
      margin-bottom: 8px;
      font-weight: bold;
    }

    select, button {
      width: 100%;
      padding: 10px;
      border: none;
      border-radius: 5px;
      margin-bottom: 15px;
      font-size: 16px;
    }

    select {
      background-color: #222;
      color: #fff;
    }

    button {
      background-color: #00ffcc;
      color: #000;
      cursor: pointer;
      font-weight: bold;
    }

    #result {
      margin-top: 30px;
      font-size: 1.2em;
      color: #00ffcc;
    }
  </style>
</head>
<body>

  <h1>Calorie Count by A</h1>

  <div class="form-group">
    <label for="gender">Select Gender:</label>
    <select id="gender">
      <option value="">-- Choose Gender --</option>
      <option value="male">Male</option>
      <option value="female">Female</option>
      <option value="other">Other</option>
    </select>
  </div>

  <div class="form-group">
    <label for="age">Select Age Range:</label>
    <select id="age">
      <option value="">-- Choose Age Range --</option>
      <option value="under18">Under 18</option>
      <option value="18to30">18 - 30</option>
      <option value="31to50">31 - 50</option>
      <option value="above50">Above 50</option>
    </select>
  </div>

  <div class="form-group">
    <label for="food">Select Food:</label>
    <select id="food">
      <option value="">-- Choose Food --</option>
      <option value="apple">Apple (95 cal)</option>
      <option value="banana">Banana (105 cal)</option>
      <option value="rice">Rice (200 cal)</option>
      <option value="chicken">Chicken (250 cal)</option>
      <option value="bread">Bread (80 cal)</option>
      <option value="egg">Egg (70 cal)</option>
    </select>
  </div>

  <button onclick="calculateCalories()">Calculate Calories</button>

  <div id="result"></div>

  <script>
    const foodCalories = {
      "apple": 95,
      "banana": 105,
      "rice": 200,
      "chicken": 250,
      "bread": 80,
      "egg": 70
    };

    function calculateCalories() {
      const gender = document.getElementById('gender').value;
      const age = document.getElementById('age').value;
      const food = document.getElementById('food').value;

      if (!gender || !age || !food) {
        document.getElementById('result').innerHTML = "Please select all options.";
        return;
      }

      const calories = foodCalories[food];
      document.getElementById('result').innerHTML =
        `You selected: ${food} → Estimated Calories: <strong>${calories}</strong> kcal`;
    }
  </script>

</body>
</html>
