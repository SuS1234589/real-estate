<script>
  // This is the logo import
  import '@fortawesome/fontawesome-free/css/all.min.css';
  
  // This is for the Navbar (i think, already forgot)
  import { onMount } from 'svelte';

  let scrolled = false;

  onMount(() => {
    window.addEventListener('scroll', handleScroll);
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });

  function handleScroll() {
    scrolled = window.scrollY > 0;
  }

  // This is the counter
  let count = 0;
  const increaseCount = () => {
    count++;
  };

  onMount(() => {
    increaseCount();
  });
  
</script>

<!-- Navbar -->

<nav class="{scrolled ? 'scrolled' : ''}">
  <div class="nav-container">
    <div class="nav-logo">Your Company</div>
    <div class="nav-links">
      <a href="#counter">Counter</a>
      <a href="#services">Our Services</a>
      <a href="#contact">Contact Us</a>
      <a href="#schedule">Schedule a Meeting</a>
    </div>
  </div>
</nav>

<!-- Main Body -->

<main>
  <section id="company name" class="section" style="padding-top: 100px;">
    <div class="section-content">
      <h1>Company Name</h1>
    </div>
  </section>

  <section id="counter" class="section">
    <div class="section-content">
      <h2>Visitors: {count}</h2>
    </div>
  </section>

  <section id="About Us" class="section">
    <div class="section-content">
      <h2>About Us</h2>
      <p>This is the About Us section. Describe your story or your background.</p>
    </div>
  </section>

  <section id="services" class="section">
    <div class="section-content">
      <h2>Our Services</h2>
      <p>This is the Our Services section. Describe your services or products here.</p>
    </div>
  </section>

  <section id="schedule" class="section">
    <div class="section-content">
      <h2>Schedule a Meeting</h2>
      <p>This is the Schedule a Meeting section. Allow visitors to schedule appointments or meetings.</p>
    </div>
  </section>
</main>

<!-- Footer -->
<footer class="footer">
  <div class="container">
    <div class="row">
        <div class="col-md-4">
          <h4>Contact Info</h4>
          <p>Email: info@example.com<br>Phone: +1 (123) 456-7890</p>
        </div>
        <!-- This is the logo part -->
        <a href="https://twitter.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-twitter"></i></a>
        <a href="https://facebook.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-facebook-f"></i></a>
        <a href="https://instagram.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-instagram"></i></a>
    </div>
  </div>
</footer>

<style>
  /* This is nav style */
  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    background-color: #ffffff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
  }

  nav.scrolled {
    background-color: #f8f8f8;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    height: 60px;
  }

  .nav-logo {
    font-size: 20px;
    font-weight: bold;
  }

  .nav-links a {
    margin-left: 20px;
    text-decoration: none;
    color: #333333;
    transition: color 0.3s ease;
  }

  .nav-links a:hover {
    color: #007bff;
  }

  /* This is the main body style */
  main {
    padding: 20px;
  }

  .section {
    margin-bottom: 40px;
  }

  .section-content {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
  }

  /* This is the footer style */
  .footer {
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
  }
  .footer a {
    color: white;
    margin: 0 10px;
    text-decoration: none;
    font-size: 24px;
  }
  .footer a:hover {
    color: #ddd;
  }
</style>
