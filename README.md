<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Music Video Showcase</title>

<style>
/* REQUIREMENT B: Custom CSS Styling */
body {
background-color: #1a1a2e; /* Dark theme background */
color: #ffffff; /* White text color */
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Custom font */
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
min-height: 100vh;
margin: 0;
overflow-x: hidden;
}

h1 {
color: #e94560; /* Accent color for the title */
margin-bottom: 20px;
}

/* Container for the YouTube video */
.video-container {
box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.5);
border-radius: 10px;
overflow: hidden;
margin-bottom: 30px;
}

/* REQUIREMENT C: Box to be animated by JavaScript */
#animated-box {
position: relative;
width: 100px;
height: 50px;
background-color: #0f969c;
border-radius: 5px;
display: flex;
align-items: center;
justify-content: center;
font-weight: bold;
font-size: 14px;
}
</style>
</head>
<body>

<!-- REQUIREMENT A: Title and Embedded YouTube Video -->
<h1>My Favorite Music Video</h1>

<div class="video-container">
<!-- Replace the VIDEO_ID with your chosen YouTube video ID -->
<iframe width="560" height="315"
src="https://youtube.com"
title="YouTube video player"
frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen>
</iframe>
</div>

<!-- JavaScript Target Element -->
<div id="animated-box">Rock On!</div>

<script>
// REQUIREMENT C: JavaScript Animation
const box = document.getElementById('animated-box');
let position = 0;
let direction = 1;
const speed = 2; // Speed of animation
const maxMovement = 150; // Maximum distance to slide left/right

function animate() {
position += speed * direction;

// Reverse direction if limits are reached
if (position > maxMovement || position < -maxMovement) {
direction *= -1;
}

// Move the box horizontally using transform
box.style.transform = `translateX(${position}px)`;

// Loop the animation smoothly
requestAnimationFrame(animate);
}

// Start the animation loop
animate();
</script>

</body>
</html>
