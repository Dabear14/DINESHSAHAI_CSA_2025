---
layout: base
title: Student Home 
description: Home Page
hide: true
---

<nav style="background-color: #2c3e50; padding: 10px 0;">
    <ul style="list-style: none; margin: 0; padding: 0; display: flex; justify-content: center; gap: 20px;">
    <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/09/03/Minigame.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px;">MiniGame</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/08/28/Hacks-Summary.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px;">Sprints</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/08/24/capture.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px;">Captures</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/" style="text-decoration: none; color: #ecf0f1; font-size: 18px;">Home Page</a></li>
    </ul>
</nav>

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
