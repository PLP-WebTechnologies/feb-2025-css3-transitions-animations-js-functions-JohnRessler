# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

## Create a CSS animation.
/* Define a keyframe animation */
@keyframes changeColor {
  0% { background-color: blue; transform: scale(1); }
  50% { background-color: green; transform: scale(1.1); }
  100% { background-color: red; transform: scale(1); }
}

/* Apply the animation to a button */
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  animation: changeColor 2s ease-in-out infinite;
}

button:hover {
  animation: changeColor 1s ease-out;
}

## Store data in localStorage.
// Store user preference in localStorage
function storePreference(theme) {
  localStorage.setItem('theme', theme);
  applyTheme();
}

// Retrieve the user preference from localStorage
function applyTheme() {
  const savedTheme = localStorage.getItem('theme');
  const body = document.body;

  if (savedTheme === 'dark') {
    body.style.backgroundColor = 'black';
    body.style.color = 'white';
  } else {
    body.style.backgroundColor = 'white';
    body.style.color = 'black';
  }
}

// Call applyTheme() when the page loads to check the stored preference
document.addEventListener('DOMContentLoaded', applyTheme);

// Button to toggle theme
document.getElementById('toggleTheme').addEventListener('click', function() {
  const currentTheme = localStorage.getItem('theme');
  if (currentTheme === 'dark') {
    storePreference('light');
  } else {
    storePreference('dark');
  }
});

## Apply JavaScript to trigger animations.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations & Local Storage</title>
  <style>
    /* CSS from the earlier example */
    @keyframes changeColor {
      0% { background-color: blue; transform: scale(1); }
      50% { background-color: green; transform: scale(1.1); }
      100% { background-color: red; transform: scale(1); }
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      animation: changeColor 2s ease-in-out infinite;
    }

    button:hover {
      animation: changeColor 1s ease-out;
    }
  </style>
</head>
<body>
  <h1>CSS Animation and JavaScript Interaction</h1>
  <button id="toggleTheme">Toggle Theme</button>
  <p>Click the button to change the theme.</p>

  <script>
    // JavaScript from the earlier example
    function storePreference(theme) {
      localStorage.setItem('theme', theme);
      applyTheme();
    }

    function applyTheme() {
      const savedTheme = localStorage.getItem('theme');
      const body = document.body;

      if (savedTheme === 'dark') {
        body.style.backgroundColor = 'black';
        body.style.color = 'white';
      } else {
        body.style.backgroundColor = 'white';
        body.style.color = 'black';
      }
    }

    document.addEventListener('DOMContentLoaded', applyTheme);

    document.getElementById('toggleTheme').addEventListener('click', function() {
      const currentTheme = localStorage.getItem('theme');
      if (currentTheme === 'dark') {
        storePreference('light');
      } else {
        storePreference('dark');
      }
    });
  </script>
</body>
</html>


