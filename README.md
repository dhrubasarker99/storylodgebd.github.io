<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>StoryLodge Bangladesh</title>
  <style>
    body {
      margin: 0;
      background-color: #000;
      color: #fff;
      font-family: Arial, sans-serif;
      scroll-behavior: smooth;
    }
    header {
      text-align: center;
      padding: 60px 20px;
    }
    header h1 {
      font-size: 48px;
      color: #00bfff;
    }
    nav {
      display: flex;
      justify-content: center;
      background-color: #111;
      padding: 10px 0;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover {
      color: #00bfff;
    }
    section {
      padding: 60px 20px;
      text-align: center;
    }
    .featured {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .album {
      position: relative;
      width: 300px;
      height: 200px;
      overflow: hidden;
      border: 2px solid #00bfff;
    }
    .album img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.5s;
    }
    .album:hover img {
      transform: scale(1.1);
      opacity: 0.7;
    }
    .album-text {
      position: absolute;
      bottom: 10px;
      left: 10px;
      background-color: rgba(0, 191, 255, 0.7);
      padding: 5px 10px;
      border-radius: 5px;
      opacity: 0;
      transition: 0.5s;
      color: black;
      font-weight: bold;
    }
    .album:hover .album-text {
      opacity: 1;
    }
    .testimonials {
      background-color: #111;
      padding: 40px;
      border-radius: 10px;
      margin: 20px auto;
      max-width: 800px;
    }
    .testimonial {
      margin-bottom: 20px;
      font-style: italic;
    }
    form {
      max-width: 500px;
      margin: auto;
      display: flex;
      flex-direction: column;
    }
    input, textarea {
      margin-bottom: 15px;
      padding: 10px;
      border: none;
      border-radius: 5px;
    }
    button {
      background-color: #00bfff;
      color: black;
      padding: 10px;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }
    button:hover {
      background-color: #0099cc;
    }
  </style>
</head>
<body>

<header>
  <h1>StoryLodge Bangladesh</h1>
  <p>Capturing Moments, Creating Memories</p>
</header>

<nav>
  <a href="#home">Home</a>
  <a href="#portfolio">Portfolio</a>
  <a href="#about">About</a>
  <a href="#packages">Packages</a>
  <a href="#book">Book Us</a>
</nav>

<section id="home">
  <h2>Featured Albums</h2>
  <div class="featured">
    <div class="album">
      <img src="https://via.placeholder.com/300x200" alt="Wedding">
      <div class="album-text">Hindu Wedding</div>
    </div>
    <div class="album">
      <img src="https://via.placeholder.com/300x200" alt="Wedding">
      <div class="album-text">Muslim Wedding</div>
    </div>
    <div class="album">
      <img src="https://via.placeholder.com/300x200" alt="Birthday">
      <div class="album-text">Birthday Events</div>
    </div>
  </div>
</section>

<section id="portfolio">
  <h2>Our Portfolio</h2>
  <p>Coming soon...</p>
</section>

<section id="about">
  <h2>About StoryLodge</h2>
  <p>We are a premium wedding photography and event coverage company, telling stories through our lens...</p>
</section>

<section id="packages">
  <h2>Our Packages</h2>
  <p>Various options available to suit your needs - Basic, Premium, and Deluxe Packages.</p>
</section>

<section id="book">
  <h2>Book Us</h2>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Your Email" required>
    <input type="text" placeholder="Mobile Number" required>
    <textarea rows="5" placeholder="Event Details & Date" required></textarea>
    <button type="submit">Submit</button>
  </form>
</section>

<footer style="text-align: center; padding: 20px; background-color: #111;">
  <p>&copy; 2025 StoryLodge Bangladesh. All rights reserved.</p>
</footer>

</body>
</html>
