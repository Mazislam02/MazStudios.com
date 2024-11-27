<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Photography Website</title>
    <style>
        /* General Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            padding: 1em 0;
            text-align: center;
        }

        /* Navigation Menu Styles */
        .navbar {
            background-color: #444;
            overflow: hidden;
        }

        .navbar ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        .navbar li {
            position: relative;
        }

        .navbar a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 14px 20px;
        }

        .navbar a:hover {
            background-color: #555;
        }

        .dropdown {
            display: none;
            position: absolute;
            background-color: #666;
            top: 100%;
            left: 0;
            min-width: 150px;
            z-index: 1000;
        }

        .dropdown a {
            padding: 10px 15px;
        }

        .navbar li:hover .dropdown {
            display: block;
        }

        /* Slider Styles */
        .slider {
            max-width: 100%;
            margin: 20px auto;
            position: relative;
            overflow: hidden;
        }

        .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .slides img {
            width: 100%;
        }

        .slider-controls {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }

        .slider-controls button {
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
        }

        /* Gallery Section Styles */
        .gallery {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 15px;
            padding: 20px;
            background: white;
        }

        .gallery img {
            width: 200px;
            height: 150px;
            object-fit: cover;
            border-radius: 8px;
        }

        /* About Section Styles */
        .about {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* Contact Section Styles */
        .contact {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* Footer Styles */
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <h1>Photography Website</h1>
    </header>

    <!-- Navigation Menu -->
    <nav class="navbar">
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#about">About Me</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Slider Section -->
    <div id="home" class="slider">
        <div class="slides">
            <img src="https://via.placeholder.com/800x400?text=Photo+1" alt="Slide 1">
            <img src="https://via.placeholder.com/800x400?text=Photo+2" alt="Slide 2">
            <img src="https://via.placeholder.com/800x400?text=Photo+3" alt="Slide 3">
            <img src="https://via.placeholder.com/800x400?text=Photo+4" alt="Slide 4">
        </div>
        <div class="slider-controls">
            <button id="prev">❮</button>
            <button id="next">❯</button>
        </div>
    </div>

    <!-- Gallery Section -->
    <div id="gallery" class="gallery">
        <img src="https://via.placeholder.com/200x150?text=Gallery+1" alt="Gallery Image 1">
        <img src="https://via.placeholder.com/200x150?text=Gallery+2" alt="Gallery Image 2">
        <img src="https://via.placeholder.com/200x150?text=Gallery+3" alt="Gallery Image 3">
        <img src="https://via.placeholder.com/200x150?text=Gallery+4" alt="Gallery Image 4">
    </div>

    <!-- About Me Section -->
    <div id="about" class="about">
        <h2>About Me</h2>
        <p>Hi, I'm <strong>Mazharul Marzan</strong>, a passionate photographer who loves capturing beautiful moments through the lens. I've been into photography for over 10 years and enjoy shooting landscapes, portraits, and everything in between. I'm always looking for new challenges and ways to improve my craft. If you'd like to work with me, feel free to reach out through my contact page!</p>
    </div>

    <!-- Contact Section -->
    <div id="contact" class="contact">
        <h2>Contact Me</h2>
        <p>If you'd like to reach out, feel free to email me at: <a href="mailto:mazharulmarzan@gmail.com">mazharulmarzan@gmail.com</a></p>
    </div>

    <script>
        // Slider Functionality
        let currentIndex = 0;
        const slides = document.querySelector('.slides');
        const slideImages = document.querySelectorAll('.slides img');

        document.getElementById('next').addEventListener('click', () => {
            currentIndex = (currentIndex + 1) % slideImages.length;
            updateSlider();
        });

        document.getElementById('prev').addEventListener('click', () => {
            currentIndex = (currentIndex - 1 + slideImages.length) % slideImages.length;
            updateSlider();
        });

        function updateSlider() {
            slides.style.transform = `translateX(-${currentIndex * 100}%)`;
        }
    </script>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Photography Website</p>
    </footer>
</body>
</html>
