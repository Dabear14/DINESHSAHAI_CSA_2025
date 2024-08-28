---
layout: base
title: Student Home 
description: Home Page
hide: true
---

<style>
    body {
        background-color: #1D428A;
        color: #FFC72C; 
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
    }

    h1, h2, h3, h4, h5, h6 {
        color: #FFC72C; 
    }

    a {
        color: #FFC72C; 
        text-decoration: none;
    }

    a:hover {
        color: #006BB6; 
    }

    #nameDisplay {
        font-size: 14px; 
        font-family: Arial, sans-serif; 
        color: #FFC72C; 
    }

    #calculator {
        max-width: 200px; 
        margin: 20px auto;
        background-color: #006BB6; 
        padding: 15px;
        border-radius: 8px;
    }

    #display {
        width: 100%; 
        padding: 10px; 
        font-size: 18px; 
        text-align: right;
        background-color: #1D428A; 
        color: #FFC72C; 
        border: none;
        border-radius: 4px;
    }

    button {
        padding: 10px;
        font-size: 18px;
        background-color: #FFC72C; 
        color: #1D428A; 
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }

    button:hover {
        background-color: #FFB81C; 
    }
</style>

My journey starts here.

<!-- -->
<div id="nameDisplay"></div>

<script>
    const name = "My name is Dinesh Sahai, I am a CSA student at Del Norte High School";
    const displayElement = document.getElementById('nameDisplay');
    let index = 0;

    function typeCharacter() {
        if (index < name.length) {
            displayElement.textContent += name.charAt(index);
            index++;
            setTimeout(typeCharacter, 75); 
        }
    }

    typeCharacter();
</script>

<div id="calculator">
    <input type="text" id="display" disabled>
    <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 5px; margin-top: 10px;">
        <button onclick="appendNumber('7')">7</button>
        <button onclick="appendNumber('8')">8</button>
        <button onclick="appendNumber('9')">9</button>
        <button onclick="appendOperator('/')">/</button>

        <button onclick="appendNumber('4')">4</button>
        <button onclick="appendNumber('5')">5</button>
        <button onclick="appendNumber('6')">6</button>
        <button onclick="appendOperator('*')">*</button>

        <button onclick="appendNumber('1')">1</button>
        <button onclick="appendNumber('2')">2</button>
        <button onclick="appendNumber('3')">3</button>
        <button onclick="appendOperator('-')">-</button>

        <button onclick="appendNumber('0')">0</button>
        <button onclick="clearDisplay()">C</button>
        <button onclick="calculateResult()">=</button>
        <button onclick="appendOperator('+')">+</button>
    </div>
</div>

<script>
    const display = document.getElementById('display');
    
    function appendNumber(number) {
        display.value += number;
    }

    function appendOperator(operator) {
        display.value += ' ' + operator + ' ';
    }

    function clearDisplay() {
        display.value = '';
    }

    function calculateResult() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = 'Error';
        }
    }
</script>
