# Ex05 Image Carousel
## Date:17/05/2025

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

## app.jsx

```
import React, { useState } from 'react';
import './App.css';

const images = [
  '/1.png',
  '/akatsuki.jpg'
];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="app">
      <h1 className="title">Anime Carousel </h1>
      <div className="carousel">
        <img src={images[index]} alt="Anime" className="carousel-image" />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
    </div>
  );
}

export default App;

```

## app.css

```
.carousel-container {
  text-align: center;
  background-color: #df6464;
  color: white;
  min-height: 100vh;
  padding: 20px;
  font-family: Arial, sans-serif;
  
}

.carousel-image {
  width: 600px;
  height: 400px;
  object-fit: cover;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.2);
}

.nav-buttons {
  margin-top: 20px;
}

.nav-buttons button {
  padding: 10px 20px;
  margin: 0 10px;
  font-size: 16px;
  background-color: #f0a500;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  color: #fff;
  transition: background 0.3s;
}

.nav-buttons button:hover {
  background-color: #d48806;
}

.dots {
  margin-top: 15px;
}

.dot {
  height: 12px;
  width: 12px;
  margin: 0 5px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.3s;
  cursor: pointer;
}

.dot.active {
  background-color: #f0a500;
}

.app {
  text-align: center;
  padding: 20px;
}

.carousel {
  display: flex;
  justify-content: center; /* Center horizontally */
  align-items: center;     /* Center vertically */
  height: 400px;           /* Adjust as needed */
}

.carousel-image {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.buttons {
  margin-top: 20px;
}

.app {
  text-align: center;
  padding: 20px;
  min-height: 100vh;
  background-color: #81aec1;
  color: white;           

```


## OUTPUT

![Screenshot 2025-05-17 134909](https://github.com/user-attachments/assets/7f06b3d8-7318-4e3a-b47a-87d522504595)

![Screenshot 2025-05-17 135242](https://github.com/user-attachments/assets/435cb300-5bf2-45a3-9af4-fe263b6abea8)



## RESULT
The program for creating Image Carousel using React is executed successfully.
