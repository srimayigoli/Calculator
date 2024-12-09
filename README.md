# Calculator.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="calculator">
    <div class="display" id="display">0</div>
    <div class="buttons">
      <div class="button clear">C</div>
      <div class="button">/</div>
      <div class="button">*</div>
      <div class="button">7</div>
      <div class="button">8</div>
      <div class="button">9</div>
      <div class="button">-</div>
      <div class="button">4</div>
      <div class="button">5</div>
      <div class="button">6</div>
      <div class="button">+</div>
      <div class="button">1</div>
      <div class="button">2</div>
      <div class="button">3</div>
      <div class="button equal">=</div>
      <div class="button">0</div>
      <div class="button">.</div>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
# Calculator.css
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f8ff;
  }
  
  .calculator {
    width: 300px;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    overflow: hidden;
  }
  
  .display {
    background-color: #222;
    color: rgb(255, 230, 0);
    font-size: 2rem;
    text-align: right;
    padding: 10px;
    border-bottom: 1px solid #333;
    height: 60px;
    word-wrap: break-word;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background-color: #333333;
  }
  
  .button {
    background-color: #444;
    color: rgb(255, 255, 255);
    font-size: 1.5rem;
    padding: 20px;
    text-align: center;
    cursor: pointer;
    user-select: none;
  }
  
  .button:active {
    background-color: #666;
  }
  
  .button.clear {
    grid-column: span 2;
    background-color: #4fd0d9c2;
  }
  
  .button.equal {
    grid-column: span 2;
    background-color: #5ca6b8;
  }
  # Calculator.js
  const display = document.getElementById('display');


document.querySelectorAll('.button').forEach(button => {
  button.addEventListener('click', () => {
    const value = button.textContent;
    if (value === 'C') {
      display.textContent = '0';
    } else if (value === '=') {
      try {
        display.textContent = eval(display.textContent);
      } catch (error) {
        display.textContent = 'Error';
      }
    } else { 
      if (display.textContent === '0' || display.textContent === 'Error') {
        display.textContent = value;
      } else {
        display.textContent += value;
      }
    }
  });
});
