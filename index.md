<html lang="{{ page.lang | default: site.lang | default: 'en' }}">
<head>
    <style>
        /* Sidebar styles */
        .sidebar {
            position: fixed;
            top: 0;
            left: 0;
            width: 200px;
            height: 100%;
            background-color: #ff69b4;
            padding: 20px;
            color: white;
            font-family: 'Arial', sans-serif;
            box-shadow: 2px 0 8px rgba(0, 0, 0, 0.1);
        }
        .sidebar h3 {
            color: white;
            margin-bottom: 20px;
            font-size: 22px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
        }
        .sidebar ul {
            list-style-type: none;
            padding: 0;
        }
        .sidebar ul li {
            margin: 10px 0;
        }
        .sidebar ul li a {
            color: white;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s ease;
        }
        .sidebar ul li a:hover {
            color: #fff;
            text-decoration: underline;
        }
        ul.post-items {
        display: none; 
        }
        /* Main content styles */
        .main-content {
            margin-left: 270px;
            padding: 20px;
        }
        /* Pink professional theme */
        .pink-title {
            color: #ff69b4;
            font-family: 'Arial', sans-serif;
            font-size: 28px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        .smiles-input {
            width: 300px;
            padding: 10px;
            font-size: 16px;
            border: 2px solid #bdc3c7;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .btn-pink {
            padding: 10px 20px;
            font-size: 16px;
            color: white;
            background-color: #ff69b4;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .btn-pink:hover {
            background-color: #ff1493;
        }
        .calculator {
            max-width: 200px;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding: 10px;
        }
        #display {
            width: 100%;
            padding: 10px;
            font-size: 18px;
            text-align: right;
            border: 2px solid #ff69b4;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .calculator button {
            padding: 10px;
            font-size: 16px;
            background-color: #ff69b4;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .calculator button:hover {
            background-color: #ff1493;
        }
        .viewer {
            width: 600px;
            height: 400px;
            border: 1px solid #ccc;
            margin-top: 20px;
            background-color: black;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .loading-indicator {
            width: 600px;
            height: 400px;
            display: none;
            justify-content: center;
            align-items: center;
            background-color: #ecf0f1;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .error-fallback {
            width: 600px;
            height: 400px;
            border: 1px solid #e74c3c;
            margin-top: 20px;
            display: none;
            color: #e74c3c;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .random-image {
            position: absolute;
            transition: left 1s ease, top 1s ease; 
        }
        .random-icon {
            width: 50px;
            height: 50px;
        }
        .spinner {
            width: 20px;
            height: 20px;
            border: 3px solid rgba(0, 0, 0, 0.1);
            border-top-color: #3498db;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }
    </style>
</head>
<body>
    <!-- Sidebar Container -->
    <div class="sidebar">
        <h3>Menu</h3>
        <ul class="sidebar-items">
            <li><a href="#" class="sidebar-link">Home</a></li>
            <li><a href="#" class="sidebar-link">Projects</a></li>
            <li><a href="http://127.0.0.1:4100/DINESHSAHAI_CSA_2025/about/" class="sidebar-link">About</a></li>
            <li><a href="http://localhost:4100/DINESHSAHAI_CSA_2025/2024/09/03/Minigame.html" class="sidebar-link">Minigame</a></li>
            <li><a href="http://localhost:4100/DINESHSAHAI_CSA_2025/navigation/2024-10-10-sprint2.html" class="sidebar-link">Latest Sprint</a></li>
        </ul>
    </div>
    <div class="main-content">
        <div style="text-align: center; margin-top: 50px;">
            <h2 class="pink-title">My journey starts here.</h2>
            <div id="nameDisplay" style="font-size: 24px; color: #ff69b4;"></div>
        </div>
        <div class="calculator">
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
        <div id="randomImage" onclick="sayRandomText();" style="position: absolute; cursor: pointer; z-index: 9999;">
            <img src="{{ site.baseurl }}/images/mort.png" alt="Random Icon" style="width: 50px; height: 50px;" />
        </div>
    </div>
    <script>
        // Display name animation
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
        // Calculator functionality
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
    // Random image movement with smooth transition
    const randomImage = document.getElementById('randomImage');
    function moveRandomImage() {
        // Calculate new random positions
        const newX = Math.floor(Math.random() * (window.innerWidth - 50));
        const newY = Math.floor(Math.random() * (window.innerHeight - 50));
        // Set the new position with CSS transitions for smooth movement
        randomImage.style.transition = 'left 1s ease, top 1s ease'; // Duration of the transition
        randomImage.style.left = newX + 'px';
        randomImage.style.top = newY + 'px';
        // Call this function again after a delay
        setTimeout(moveRandomImage, 2000);
    }
    // Initialize position and start the movement
    randomImage.style.position = 'absolute';
    moveRandomImage();
    function sayRandomText() {
        const messages = ["Code Code Code"];
        const randomMessage = messages[Math.floor(Math.random() * messages.length)];
        const synth = window.speechSynthesis;
        const utterThis = new SpeechSynthesisUtterance(randomMessage);
        synth.speak(utterThis);
    }
        document.addEventListener("DOMContentLoaded", function() {
        const postList = document.querySelector('ul.post-list');
        if (postList) {
            postList.style.display = 'none'; // Hide the list
        }
    }); 
    </script>
</body>
</html>