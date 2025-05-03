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
Calculator.jsx
```
import React, { useState } from 'react';

const Calculator = () => {
  const [height, setHeight] = useState('');
  const [weight, setWeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    const heightInMeters = height / 100;
    const calculatedBmi = weight / (heightInMeters ** 2);
    setBmi(calculatedBmi);
    categorizeBmi(calculatedBmi);
  };

  const categorizeBmi = (bmi) => {
    if (bmi < 18.5) {
      setCategory('Underweight');
    } else if (bmi < 24.9) {
      setCategory('Normal weight');
    } else if (bmi < 29.9) {
      setCategory('Overweight');
    } else {
      setCategory('Obesity');
    }
  };

  return (
    <div>
      <h2>BMI Calculator</h2>
      <form onSubmit={handleSubmit}>
        <input
          type="number"
          placeholder="Height (in cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
          required
        />
        <input
          type="number"
          placeholder="Weight (in kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
          required
        />
        <button type="submit">Calculate</button>
      </form>
      {bmi !== null && (
        <div>
          <h3>Your BMI: {bmi.toFixed(2)}</h3>
          <p>Category: {category}</p>
        </div>
      )}
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
App.jsx
```
import React from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import Home from './Home';
import Calculator from './Calculator';

const App = () => {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/calculator" element={<Calculator />} />
      </Routes>
    </Router>
  );
};

export default App;

```

## OUTPUT
![image](https://github.com/user-attachments/assets/97e5f426-5bb4-48bf-807d-58bfb69b9581)
![image](https://github.com/user-attachments/assets/7d4eda83-2128-46a0-9e05-299592d6d333)


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
