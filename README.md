# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dynamic DOM Interaction</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1 id="main-heading">Welcome to My Page</h1>
  </header>

  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </nav>

  <main>
    <section>
      <p id="description">Click the button below to see some JavaScript magic!</p>
      <button id="action-btn">Do Something</button>
    </section>
    <section id="dynamic-section">
      <!-- Element will be added/removed here -->
    </section>
  </main>

  <footer>
    <p>&copy; 2025 My Website</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
/* Global Styles */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f0f8ff;
  color: #333;
  line-height: 1.6;
}

/* Header */
header {
  background-color: #004080;
  color: white;
  padding: 1rem;
  text-align: center;
}

h1 {
  margin: 0;
}

/* Navigation */
nav {
  background-color: #e6f2ff;
  padding: 0.5rem 1rem;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
  padding: 0;
  margin: 0;
}

nav a {
  text-decoration: none;
  color: #004080;
  font-weight: bold;
}

nav a:hover {
  text-decoration: underline;
}

/* Main Content */
main {
  padding: 2rem;
}

section {
  margin-bottom: 2rem;
}

/* Button */
#action-btn {
  background-color: #007acc;
  color: white;
  border: none;
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  cursor: pointer;
  border-radius: 5px;
}

#action-btn:hover {
  background-color: #005f99;
}

/* Dynamic Element */
#magic-box {
  margin-top: 1rem;
  background-color: #dff0d8;
  border: 1px solid #b2d8b2;
  padding: 1rem;
  border-radius: 4px;
  animation: fadeIn 0.5s ease-in-out;
}

/* Footer */
footer {
  background-color: #004080;
  color: white;
  text-align: center;
  padding: 1rem;
  position: sticky;
  bottom: 0;
  width: 100%;
}

/* Animation */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

// Change text content
document.getElementById("main-heading").textContent = "Jummy Hamdalat Made This!";

// Modify CSS styles
document.body.style.backgroundColor = "#f0f8ff";
document.getElementById("description").style.color = "teal";

// Add/remove an element on button click
const button = document.getElementById("action-btn");
const dynamicSection = document.getElementById("dynamic-section");
let isAdded = false;

button.addEventListener("click", () => {
  if (!isAdded) {
    const newElement = document.createElement("div");
    newElement.id = "magic-box";
    newElement.textContent = "✨ I'm a new element!";
    newElement.style.padding = "10px";
    newElement.style.backgroundColor = "#dff0d8";
    newElement.style.border = "1px solid #b2d8b2";
    dynamicSection.appendChild(newElement);
    isAdded = true;
  } else {
    const element = document.getElementById("magic-box");
    if (element) dynamicSection.removeChild(element);
    isAdded = false;
  }
});



