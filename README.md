<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Advanced Navbar</title>
  <link rel="stylesheet" href="style.css" />
  <script defer src="script.js"></script>
</head>
<body>
  <header class="navbar" id="navbar">
    <div class="logo">MyBrand</div>
    <nav class="nav-links" id="navLinks">
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    <div class="hamburger" id="hamburger">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>

  <main>
    <section class="hero">
      <h1>Welcome to My Website</h1>
      <p>Scroll down to see navbar effect</p>
    </section>
 <section class="testimonials" id="testimonials">
  <h2>What People Say About Skillcraft Technology</h2>
  
  <div class="testimonial-box">
    <p>"Skillcraft Technology transformed the way I think about learning. Their practical projects helped me get real results!"</p>
  </div>
  <div class="testimonial-box">
    <p>"Amazing experience! The mentors are supportive and the tasks are industry-relevant. Loved the hands-on approach."</p>
  </div>
  <div class="testimonial-box">
    <p>"I built my first full-stack app thanks to Skillcraft. The best decision I made in my tech journey!"</p>
  </div>
  <div class="testimonial-box">
    <p>"They make learning exciting and productive. I felt confident in front-end, back-end, and even data science!"</p>
  </div>
 </section>

    <section class="content">
      <p>This is some sample content to demonstrate scroll behavior. Keep scrolling...</p>
      <div style="height: 1200px;"></div>
    </section>
  </main>
</body>
</html>


SCRIPT.JS

const hamburger = document.getElementById('hamburger');
const navLinks = document.getElementById('navLinks');
const navbar = document.getElementById('navbar');

hamburger.addEventListener('click', () => {
  navLinks.classList.toggle('open');
});

// Change navbar color on scroll
window.addEventListener('scroll', () => {
  if (window.scrollY > 50) {
    navbar.classList.add('scrolled');
  } else {
    navbar.classList.remove('scrolled');
  }
});


// Existing script...
const hamburger = document.getElementById('hamburger');
const navLinks = document.getElementById('navLinks');
const navbar = document.getElementById('navbar');

hamburger.addEventListener('click', () => {
  navLinks.classList.toggle('open');
});

window.addEventListener('scroll', () => {
  if (window.scrollY > 50) {
    navbar.classList.add('scrolled');
  } else {
    navbar.classList.remove('scrolled');
  }

  // Reveal testimonials on scroll
  const testimonials = document.querySelectorAll('.testimonial-box');
  testimonials.forEach(box => {
    const boxTop = box.getBoundingClientRect().top;
    const windowHeight = window.innerHeight;
    if (boxTop < windowHeight - 100) {
      box.classList.add('visible');
    }
  });
});

STYLE.CSS


/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f9f9f9;
  line-height: 1.6;
}

.navbar {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  background-color: transparent;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
  z-index: 999;
}

.navbar.scrolled {
  background-color: #0d1117;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}

.logo {
  font-size: 1.6rem;
  font-weight: bold;
  color: #58a6ff;
}

.nav-links ul {
  display: flex;
  list-style: none;
  gap: 1.5rem;
}

.nav-links a {
  text-decoration: none;
  color: #c9d1d9;
  font-size: 1rem;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #58a6ff;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
}

.hamburger span {
  height: 3px;
  width: 25px;
  background-color: #ffffff;
  border-radius: 2px;
  transition: all 0.3s ease;
}

/* Mobile styles */
@media (max-width: 768px) {
  .nav-links {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #161b22;
    overflow: hidden;
    max-height: 0;
    transition: max-height 0.4s ease;
  }

  .nav-links.open {
    max-height: 400px;
  }

  .nav-links ul {
    flex-direction: column;
    text-align: center;
    padding: 1rem 0;
    gap: 1rem;
  }

  .hamburger {
    display: flex;
  }
}

/* Content styling */
.hero {
  height: 100vh;
  background: linear-gradient(135deg, #111, #222);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.content {
  padding: 2rem;
  background-color: #fff;
}

.hero h1,
.hero p {
  transition: color 0.3s ease;
}

.hero h1:hover,
.hero p:hover {
  color: #d63384; /* Dark pink */
}

.hero {
  height: 100vh;
  background: linear-gradient(135deg, #111, #222);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.hero h1,
.hero p {
  transition: color 0.3s ease;
}

.hero h1:hover,
.hero p:hover {
  color: #d63384; /* Dark pink on hover */
}

.testimonials {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
  text-align: center;
  color: #111;
}

.testimonials h2 {
  font-size: 2rem;
  margin-bottom: 2rem;
  color: #0d1117;
}

.testimonial-box {
  max-width: 800px;
  margin: 1.5rem auto;
  background-color: #ffffff;
  padding: 1.5rem 2rem;
  border-left: 5px solid #d63384;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  opacity: 0;
  transform: translateY(50px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.testimonial-box.visible {
  opacity: 1;
  transform: translateY(0);
}
