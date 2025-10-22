# MWAD-EXP_04-Simple-caluculator
## Date:22.10.25

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
```
import React, { useState } from "react";

const Calculator = () => {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    if (value === "=") {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput("Error");
      }
    } else if (value === "C") {
      setInput("");
    } else {
      setInput(input + value);
    }
  };

  // Proper calculator buttons arranged row by row
  const buttons = [
    ["C", "/", "*", "-"],
    ["7", "8", "9", "+"],
    ["4", "5", "6", "="],
    ["1", "2", "3", "."],
    ["0"]
  ];

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-900">
      <div className="bg-[#0b0f24] p-6 rounded-3xl shadow-2xl w-[320px]">
        <h1 className="text-white font-extrabold text-lg mb-4 flex items-center gap-2">
          <span role="img" aria-label="calc">🧮</span> BOLD METAL CALC
        </h1>

        <div className="bg-[#161a36] text-right text-white text-3xl font-mono p-4 rounded-xl mb-4 h-[70px] flex items-center justify-end shadow-inner">
          {input || "0"}
        </div>

        {/* Buttons Grid */}
        <div className="flex flex-col gap-3">
          {buttons.map((row, i) => (
            <div key={i} className="grid grid-cols-4 gap-3">
              {row.map((btn, j) => (
                <button
                  key={j}
                  onClick={() => handleClick(btn)}
                  className={`rounded-xl font-bold text-xl py-3 shadow-md transition-transform active:scale-95 ${
                    btn === "C"
                      ? "bg-red-500 hover:bg-red-600 text-white"
                      : btn === "="
                      ? "bg-green-500 hover:bg-green-600 text-white"
                      : ["+", "-", "*", "/"].includes(btn)
                      ? "bg-blue-600 hover:bg-blue-700 text-white"
                      : "bg-gray-700 hover:bg-gray-600 text-white"
                  } ${btn === "0" ? "col-span-2" : ""}`}
                >
                  {btn}
                </button>
              ))}
            </div>
          ))}
        </div>
      </div>
    </div>
  );
};

export default Calculator;
```



## OUTPUT
<img width="1792" height="1106" alt="Screenshot 2025-10-20 180738" src="https://github.com/user-attachments/assets/097816e1-e8c2-4fa1-bc4e-60f2f6bf30c3" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
