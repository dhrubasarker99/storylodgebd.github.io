/* General Styles */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #000;
  color: white;
}

a {
  text-decoration: none;
  color: #00BFFF;
}

ul {
  list-style: none;
}

h1, h2, h3 {
  margin: 0.5em 0;
}

/* Header Section */
header {
  background-color: #111;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header .logo h1 {
  font-size: 2.5rem;
}

header nav ul {
  display: flex;
}

header nav ul li {
  margin: 0 15px;
}

header nav ul li a {
  font-size: 1.2rem;
  color: white;
}

/* Hero Section */
.hero {
  text-align: center;
  padding: 50px 20px;
  background-color: #222;
}

.hero h2 {
  font-size: 2.5rem;
}

.hero .btn {
  background-color: #00BFFF;
  padding: 10px 20px;
  border-radius: 5px;
  color: white;
  font-size: 1.2rem;
}

/* Portfolio Section */
.portfolio {
  padding: 50px 20px;
}

.portfolio h2 {
  text-align: center;
  font-size: 2.5rem;
}

.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.category {
  width: 30%;
}

.image-grid img {
  width: 100%;
  height: auto;
  transition: transform 0.3s ease;
}

.image-grid img:hover {
  transform: scale(1.1);
}

/* Book Us Section */
.book-us {
  background-color: #333;
  padding: 50px 20px;
  text-align: center;
}

.book-us form {
  max-width: 600px;
  margin: 0 auto;
}

.book-us form input, .book-us form textarea {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.book-us form button {
  background-color: #00BFFF;
  color: white;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  font-size: 1.2rem;
  cursor: pointer;
}

/* Footer Section */
footer {
  background-color: #111;
  padding: 20px;
  text-align: center;
}

footer .social-links a {
  margin: 0 10px;
  color: white;
  font-size: 1.2rem;
}

/* Responsive Design */
@media (max-width: 768px) {
  header {
    flex-direction: column;
    text-align: center;
  }

  .gallery {
    flex-direction: column;
  }

  .category {
    width: 100%;
  }
  
  .hero h2 {
    font-size: 2rem;
  }

  .portfolio h2, .book-us h2 {
    font-size: 2rem;
  }

  .book-us form button {
    width: 100%;
  }
}
