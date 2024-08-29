---
layout: base
title: Student Home 
description: Home Page
hide: true
---

<style>
    body {
        font-family: 'Arial', sans-serif;
        background: linear-gradient(to bottom right, #000000, #ffffff);
        color: #fff;
        text-align: center;
        padding: 20px;
    }

    #nameDisplay {
        font-size: 24px;
        font-weight: bold;
        margin-top: 50px;
        color: #000080; 
        text-shadow: none; 
    }

    button {
        padding: 15px;
        font-size: 18px;
        background: #ffeb3b;
        color: #000;
        border: none;
        border-radius: 5px;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
        transition: background 0.3s ease, box-shadow 0.3s ease;
        cursor: pointer;
    }

    button:hover {
        background: #ffc107;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
    }

    input[type="text"] {
        background: rgba(255, 255, 255, 0.3);
        border: none;
        border-radius: 5px;
        color: #fff;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
    }
</style>

My journey starts here.

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

<div id="calculator" style="max-width: 200px; margin: 20px auto;">
    <input type="text" id="display" style="width: 100%; padding: 10px; font-size: 18px; text-align: right;" disabled>
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
