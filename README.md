### CODE:
## galery.html
~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Image Gallery</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="gallery-container">
    <div class="gallery">
      <div class="image-item">
        <img src="image.png" alt="Image 1">
        <div class="caption">The mountains are calling, and I must go.</div>
      </div>
      <div class="image-item">
        <img src="image copy.png" alt="Image 2">
        <div class="caption">Chasing sunsets and dreams.</div>
      </div>
      <div class="image-item">
        <img src="image copy 2.png" alt="Image 3">
        <div class="caption">Life is a climb; hold on tight.</div>
      </div>
      <div class="image-item">
        <img src="image copy 3.png" alt="Image 4">
        <div class="caption">Every ride is a journey, not a race.</div>
      </div>
      <!-- Add more images as needed -->
    </div>
    <button class="nav-button prev">&#10094;</button>
    <button class="nav-button next">&#10095;</button>
  </div>

  <footer>
    <p>SHANMUGAKARTHIK G - 212223220105</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
~~~

## scripts.js
~~~
const gallery = document.querySelector('.gallery');
const prevButton = document.querySelector('.prev');
const nextButton = document.querySelector('.next');
let currentIndex = 0;

// Function to move to the next image
nextButton.addEventListener('click', () => {
  if (currentIndex < gallery.children.length - 1) {
    currentIndex++;
  } else {
    currentIndex = 0; // Loop back to the first image
  }
  updateGallery();
});

// Function to move to the previous image
prevButton.addEventListener('click', () => {
  if (currentIndex > 0) {
    currentIndex--;
  } else {
    currentIndex = gallery.children.length - 1; // Loop to the last image
  }
  updateGallery();
});

// Function to update the gallery position
function updateGallery() {
  const offset = -currentIndex * 100;
  gallery.style.transform = `translateX(${offset}%)`;
}

// Optional: Auto-slide every 5 seconds
setInterval(() => {
  if (currentIndex < gallery.children.length - 1) {
    currentIndex++;
  } else {
    currentIndex = 0;
  }
  updateGallery();
}, 5000);
~~~

## styles.html
~~~
/* General Styles */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background-color: #f4f4f4;
  }
  
  /* Gallery Container */
  .gallery-container {
    position: relative;
    width: 80%;
    max-width: 800px;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }
  
  /* Gallery */
  .gallery {
    display: flex;
    transition: transform 0.5s ease-in-out;
  }
  
  /* Image Item */
  .image-item {
    position: relative;
    min-width: 100%;
    box-sizing: border-box;
  }
  
  .image-item img {
    width: 100%;
    display: block;
    border-radius: 10px;
  }
  
  /* Caption */
  .caption {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    color: white;
    text-align: center;
    padding: 10px;
    opacity: 0;
    transition: opacity 0.3s ease;
  }
  
  .image-item:hover .caption {
    opacity: 1;
  }
  
  /* Navigation Buttons */
  .nav-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    font-size: 18px;
    border-radius: 50%;
    transition: background-color 0.3s ease;
  }
  
  .nav-button:hover {
    background-color: rgba(0, 0, 0, 0.8);
  }
  
  .prev {
    left: 10px;
  }
  
  .next {
    right: 10px;
  }
  
  /* Footer */
  footer {
    margin-top: 20px;
    text-align: center;
    font-size: 14px;
    color: #555;
  }
~~~

### OUTPUT
![alt text](<Screenshot (76).png>)
![alt text](<Screenshot (77).png>)
![alt text](<Screenshot (78).png>)
![alt text](<Screenshot (79).png>)

http://127.0.0.1:5500/galery.html