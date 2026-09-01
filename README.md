# Ex05 Image Carousel
## Date:01.09.2026

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
main.jsx
```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```
App.jsx
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const images = [
    "https://picsum.photos/id/1015/600/400",
    "https://picsum.photos/id/1016/600/400",
    "https://picsum.photos/id/1025/600/400"
  ];

  const [index, setIndex] = useState(0);

  return (
    <div className="container">
      <h1>Image Carousel</h1>

      <img src={images[index]} alt="carousel" />

      <br />

      <button onClick={() =>
        setIndex((index - 1 + images.length) % images.length)
      }>
        Previous
      </button>

      <button onClick={() =>
        setIndex((index + 1) % images.length)
      }>
        Next
      </button>

      <h3>Vahini - 19AI545</h3>
    </div>
  );
}

export default App;
```
App.css
```
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: lightgray;
}

.container {
  text-align: center;
  padding: 40px;
}

h1 {
  color: black;
}

img {
  width: 600px;
  height: 400px;
  object-fit: cover;
  border-radius: 10px;
}

button {
  margin: 20px 10px;
  padding: 10px 20px;
  cursor: pointer;
}
```


## OUTPUT
<img width="1920" height="1080" alt="Screenshot (269)" src="https://github.com/user-attachments/assets/35cba6ce-c923-4cce-baa8-86594e006052" />
<img width="1920" height="1080" alt="Screenshot (268)" src="https://github.com/user-attachments/assets/bde89ae0-580d-444d-a275-61b15fe3a43d" />



## RESULT
The program for creating Image Carousel using React is executed successfully.
