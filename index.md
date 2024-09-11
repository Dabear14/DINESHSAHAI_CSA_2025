---
layout: base
title: Student Home 
description: Home Page
hide: true
---

<nav style="background-color: #2c3e50; padding: 15px 0; box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);">
    <ul style="list-style: none; margin: 0; padding: 0; display: flex; justify-content: center; gap: 30px;">
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/09/03/Minigame.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px; padding: 8px 15px; border-radius: 4px; transition: background-color 0.3s;">MiniGame</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/08/28/Hacks-Summary.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px; padding: 8px 15px; border-radius: 4px; transition: background-color 0.3s;">Sprints</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/2024/08/24/capture.html" style="text-decoration: none; color: #ecf0f1; font-size: 18px; padding: 8px 15px; border-radius: 4px; transition: background-color 0.3s;">Captures</a></li>
        <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/about/" style="text-decoration: none; font-size: 18px; padding: 8px 15px; border-radius: 4px; transition: background-color 0.3s;">About Me</a></li>
        
    </ul>
</nav>

<main style="padding: 20px; font-family: Arial, sans-serif; color: #34495e; text-align: center;">
    <h1 style="font-size: 24px; margin-bottom: 20px;">My journey starts here.</h1>
    <div id="nameDisplay" style="font-size: 20px; line-height: 1.5;"></div>
</main>

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

<div id="randomImage" onclick="sayRandomText();" style="position: absolute; cursor: pointer; z-index: 9999;">
        <img src="{{ site.baseurl }}/images/mort.png" alt="Random Icon" style="width: 50px; height: 50px;" />
    </div>

<script>
    // Variables to control image movement
    let posX = Math.random() * (window.innerWidth - 50);
    let posY = Math.random() * (window.innerHeight - 50);
    let velocityX = 1;
    let velocityY = 1;

    // Function to move the image
    function moveImage() {
        const image = document.getElementById('randomImage');
        const imageWidth = image.offsetWidth;
        const imageHeight = image.offsetHeight;

        // Update the position
        posX += velocityX;
        posY += velocityY;

        // Bounce off the walls
        if (posX <= 0 || posX + imageWidth >= window.innerWidth) {
            velocityX = -velocityX;
        }
        if (posY <= 0 || posY + imageHeight >= window.innerHeight) {
            velocityY = -velocityY;
        }

        // Apply the new position
        image.style.left = `${posX}px`;
        image.style.top = `${posY}px`;

        // Call the moveImage function repeatedly to keep the image moving
        requestAnimationFrame(moveImage);
    }

    // Start the image moving when the page loads
    window.onload = () => {
        moveImage();
    };

    // Function for text-to-speech on image click
    function sayRandomText() {
        const messages = ["Code, code, code!"];
        const randomMessage = messages[Math.floor(Math.random() * messages.length)];
        const synth = window.speechSynthesis;
        const utterThis = new SpeechSynthesisUtterance(randomMessage);
        synth.speak(utterThis);
    }   