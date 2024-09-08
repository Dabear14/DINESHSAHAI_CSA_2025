---
layout: page
title: About
permalink: /about/
---

### Image Gallery

<div class="gallery-container">
  <div class="gallery-slide fade">
    <img src="{{ site.baseurl }}/images/About/Me&Brother.png" style="width:100%">
  </div>

  <div class="gallery-slide fade">
    <img src="{{ site.baseurl }}/images/About/Me&Brother2.png" style="width:100%">
  </div>

  <div class="gallery-slide fade">
    <img src="{{ site.baseurl }}/images/About/Dad&Brother.png" style="width:100%">
  </div>

  <div class="gallery-slide fade">
    <img src="{{ site.baseurl }}/images/About/Me&Grandma.png" style="width:100%">
  </div>

  <div class="gallery-slide fade">
    <img src="{{ site.baseurl }}/images/About/Diwali2018.jpg" style="width:100%">
  </div>
</div>

<style>
/* Gallery container */
.gallery-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Hide all the images by default */
.gallery-slide {
  display: none;
}

/* Fading animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {opacity: .4}
  to {opacity: 1}
}

@keyframes fade {
  from {opacity: .4}
  to {opacity: 1}
}
</style>

<script>
let slideIndex = 0;
showSlides();

function showSlides() {
  let slides = document.getElementsByClassName("gallery-slide");
  for (let i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }
  slideIndex++;
  if (slideIndex > slides.length) {slideIndex = 1}
  slides[slideIndex-1].style.display = "block";
  setTimeout(showSlides, 3000); // Change image every 3 seconds
}
</script>

<h2>Some of my hobbies include photography, basketball, and cinema (movies).</h2>

<div style="display: flex; justify-content: space-around; margin: 10px 0;">
    <img src="{{ site.baseurl }}/images/About/Photography.jpg" style="border: 2px solid white; padding: 5px; width: 45%;">
    <img src="{{ site.baseurl }}/images/About/basketball.jpg" style="border: 2px solid white; padding: 5px; width: 45%;">
</div>

<h2> Here are my top three favorite movies: </h2>
<img src="{{ site.baseurl }}/images/About/Parasite.jpg" style="border: 2px solid white; padding: 5px; display: block; margin: 10px 0;">
<img src="{{ site.baseurl }}/images/About/Joker.jpg" style="border: 2px solid white; padding: 5px; display: block; margin: 10px 0;">
<img src="{{ site.baseurl }}/images/About/avengers_infinitywar.jpg" style="border: 2px solid white; padding: 5px; display: block; margin: 10px 0;">

<h2> Career Aspirations </h2>
Hi! My name is Dinesh Sahai, I am a senior at Del Norte High School and I am taking CSA. A little about my experience with programming. I first began coding for my local CyberPatriot team (CyberAegis) where I used WSL as part of my workflow on the leadership team. I also learned about bash scripting and learned the fundamentals of coding there. Since then, I've interned at UCLA and worked with deep learning algorithms in python. I have broadened my experience to bioinformatics research with the internships I've completed and I am hoping to pursue a career using the skills I will develop in CSA! I hope to become a software engineer in the future!