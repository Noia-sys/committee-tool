# committee-tool
committee-tool
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Committee Number Assignment</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; }
    button { padding: 15px 25px; font-size: 18px; cursor: pointer; }
    p { font-size: 20px; margin-top: 20px; color: green; }
  </style>
</head>
<body>
  <h1>Click to Get Your Committee Number</h1>
  <button id="getNumberBtn">Get My Number</button>
  <p id="yourNumber"></p>

  <script src="script.js"></script>
</body>
</html>
// Available numbers (change 10 to total number of members)
let availableNumbers = [];
for (let i = 1; i <= 10; i++) {
  availableNumbers.push(i);
}

const button = document.getElementById('getNumberBtn');
const output = document.getElementById('yourNumber');

button.addEventListener('click', () => {
  if (availableNumbers.length === 0) {
    output.textContent = "Sorry! All numbers are assigned.";
    button.disabled = true;
    return;
  }

  // Pick a random index
  const randomIndex = Math.floor(Math.random() * availableNumbers.length);
  const numberAssigned = availableNumbers[randomIndex];

  // Show number to user
  output.textContent = `Your Committee Number is: ${numberAssigned}`;

  // Remove the assigned number
  availableNumbers.splice(randomIndex, 1);
});
