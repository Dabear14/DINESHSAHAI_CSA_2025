---
layout: base
title: Student Home 
description: Home Page
hide: true
---

My journey starts here.

<!-- -->
<div id="nameDisplay" style="font-size: 14px; font-family: Arial, sans-serif; color: white"></div>

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