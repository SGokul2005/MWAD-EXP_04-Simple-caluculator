# MWAD-EXP_04-Simple-caluculator
## Date:2.05.2025
## Name:Gokul S
## Register No:212223040051

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
Calculator.js
```
import React, { useState } from 'react';
import './Calculator.css';

const Calculator = () => {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === 'C') {
      setInput('');
    } else {
      setInput(input + value);
    }
  };

  const buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*',
    '1', '2', '3', '-',
    '0', 'C', '=', '+'
  ];

  return (
    <div className="calculator">
      <input type="text" value={input} readOnly />
      <div className="buttons">
        {buttons.map((btn, index) => (
          <button key={index} onClick={() => handleClick(btn)}>
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
};

export default Calculator;
```
Calculator.css
```
.calculator {
    width: 300px;
    margin: 50px auto;
    background-color: #000000;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0px 0px 10px #ccc;
  }
  
  input {
    width: 100%;
    height: 40px;
    font-size: 20px;
    text-align: right;
    margin-bottom: 10px;
    padding: 10px;
    border: none;
    border-radius: 10px;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }
  
  button {
    padding: 20px;
    font-size: 18px;
    border: none;
    background-color: #f107f5;
    color: white;
    border-radius: 10px;
    cursor: pointer;
    transition: 0.2s;
  }
  
  button:hover {
    background-color: #45a049;
  }
  ```
App.js
```
import React from 'react';
import Calculator from './Calculator';

function App() {
  return (
    <div className="App">
      <h2 style={{ textAlign: 'center' }}>Simple Calculator</h2>
      <Calculator />
    </div>
  );
}

export default App;
```

## OUTPUT
![image](https://github.com/user-attachments/assets/97e5f426-5bb4-48bf-807d-58bfb69b9581)
![image](https://github.com/user-attachments/assets/7d4eda83-2128-46a0-9e05-299592d6d333)


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
