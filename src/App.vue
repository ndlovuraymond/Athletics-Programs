<script setup>
import { Mail, Phone } from 'lucide-vue-next';
import { ref, onMounted, onUnmounted } from 'vue';

const activeSection = ref("");

const observeSections = () => {
  const sections = document.querySelectorAll("section"); // Get all sections
  const options = { threshold: 0.6 }; // When 60% of the section is visible
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        activeSection.value = entry.target.id;
      }
    });
  }, options);

  sections.forEach((section) => observer.observe(section));
};

// Run when component mounts
onMounted(() => {
  observeSections();
});

onUnmounted(() => {
  // Cleanup the observer
  const sections = document.querySelectorAll("section");
  sections.forEach((section) => observer.unobserve(section));
});
</script>

<template>
  <div class="header">
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
      <div class="container-fluid">
        <a class="navbar-brand" href="#"><img src="./assets/Equilibrium-logo.png" alt="">
          &nbsp;EQUILIBRIUM</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarTogglerDemo03"
          aria-controls="navbarTogglerDemo03" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'hero' }" href="#hero">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'about' }" href="#about">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'activities' }" href="#activities">Activities &
                Events</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'achievements' }"
                href="#achievements">Achievements</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'join' }" href="#join">Join Us</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" :class="{ active: activeSection === 'contact' }" href="#contact">Contact</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <section id="hero" class="hero">
    <h1>Welcome to Equilibrium Sports & Fitness Academy</h1>
    <p>Empowering Athletes, Building Champions</p>
    <a href="#about" class="btn btn-custom btn-danger">Learn More</a>
  </section>

  <section id="about" class="section text-left">
    <div class="container d-flex flex-column flex-md-row">
      <div class="about-us-content col-12 col-md-6 d-flex flex-column">
        <h2>About Us</h2>
        <p>Equilibrium Sports & Fitness Academy is committed to cultivating a culture of athletic excellence, discipline,
          and personal growth. Our mission is to provide athletes of all skill levels with the training, support, and
          resources they need to reach their full potential. Through structured programs, expert coaching, and a
          supportive community, we aim to inspire a lifelong passion for sports and fitness.<br><br>
          At Equilibrium, we believe in the power of sports to transform lives not just by enhancing physical abilities
          but also by instilling values like teamwork, perseverance, and self confidence. Our programs cater to
          individuals seeking to improve their performance, whether for competitive events or personal fitness goals. We
          emphasize a holistic approach to training, incorporating strength and conditioning, mental resilience, and
          injury prevention to ensure long term success.<br><br>
          Beyond athletic development, we strive to create a welcoming and inclusive environment where individuals from
          all backgrounds can thrive. Whether you're an aspiring athlete, a seasoned competitor, or someone looking to
          adopt a healthier lifestyle, Equilibrium Sports and Fitness Academy is here to guide you on your journey to
          greatness.</p>
      </div>
      <div class="col-12 col-md-6 about-us-img d-flex align-items-center">
        <img src="./assets/about-us.jpg" alt="">
      </div>
    </div>
  </section>

  <section id="activities" class="section">
    <div class="container d-flex flex-column flex-md-row">
      <div class="col-6 activities-img d-none d-md-flex align-items-center">
        <img src="./assets/event.jpg" alt="">
      </div>
      <div class="col-12 col-md-6 activities-content d-flex flex-column justify-content-center">
        <h2 class="text-left">Activities & Events</h2>
        <p class="text-left">At Equilibrium Sports & Fitness Academy, we provide a diverse range of training programs
          and events designed to help athletes enhance their skills, build endurance, and achieve peak performance. Our
          offerings include:
          <br><br>
          <strong>Structured Training Sessions:</strong> Personalized coaching and group workouts focusing on strength,
          speed, and agility.<br>
          <strong>Competitive Events:</strong> Regular participation in local, regional, and national competitions to
          test and showcase athletic progress.<br>
          <strong>Fitness Workshops:</strong> Expert-led sessions on injury prevention, nutrition, and recovery
          strategies for optimal performance.<br>
          <strong>Strength & Conditioning Programs:</strong> Tailored exercise routines aimed at improving power,
          endurance, and flexibility.<br>
          <strong>Youth Development Programs:</strong> Training designed specifically for young athletes to build
          foundational skills and confidence.<br>
          <strong>Cross-Training Opportunities:</strong> Sessions incorporating different sports and exercises to
          enhance overall athleticism.<br><br>
          Our goal is to create an environment where athletes can grow, push their limits, and unlock
          their full potential.
        </p>
      </div>
      <div class="col-12 activities-img d-flex align-items-center d-md-none">
        <img src="./assets/event.jpg" alt="">
      </div>
    </div>
  </section>

  <section id="achievements" class="section text-start">
    <div class="container d-flex flex-column flex-md-row">
      <div class="col-12 col-md-6 achievements-content d-flex flex-column">
        <h2>Achievements</h2>
        <p>At Equilibrium Sports & Fitness Academy, we take pride in the remarkable accomplishments of
          our athletes.
          Through dedication, rigorous training, and expert coaching, our members have excelled in various competitions
          and earned recognition at local, regional, and national levels. Our track record speaks for itself, showcasing
          the hard work and perseverance of our athletes who continue to push their limits and achieve greatness.<br><br>

          <strong>National Championship Titles:</strong> Our athletes have secured top positions in prestigious
          national competitions, demonstrating their elite skills and determination.<br>
          <strong>Regional & State-Level Victories:</strong> Consistent podium finishes in regional and state
          tournaments across multiple disciplines.<br>
          <strong>Record-Breaking Performances:</strong> Several of our members have set new personal and event
          records, raising the bar in their respective sports.<br>
          <strong>Scholarship Opportunities:</strong> Many of our athletes have earned athletic scholarships, securing
          spots in top universities and sports programs.<br>
          <strong>International Representation:</strong> Select athletes have proudly represented their country in
          international events, competing among the best in the world.<br>
          <strong>Community Impact & Leadership:</strong> Beyond competition, our athletes actively engage in
          mentorship programs, inspiring the next generation of sports enthusiasts.<br><br>

          These achievements are a testament to the high standards of training and the supportive environment we provide.
          If you're looking to elevate your athletic journey and be part of a winning team, Equilibrium Sports & Fitness
          Academy is the place to be!
        </p>
      </div>
      <div class="col-12 col-md-6 achievements-img d-flex align-items-center">
        <img src="./assets/achievements.jpg" alt="">
      </div>
    </div>
  </section>

  <section id="join" class="section text-center">
    <div class="container">
      <h2>Join Us</h2>
      <p>Ready to elevate your game? At Equilibrium Sports & Fitness Academy, we welcome athletes of all levels who are
        passionate about sports and personal growth. Join our community, train with expert coaches, and push your limits.
        Reach out to us to get started!
      </p>
      <a href="mailto:equilibriumsports@email.com" class="btn btn-custom btn-danger">Contact Us</a>
    </div>
  </section>

  <section id="contact" class="section text-center">
    <div class="container d-flex flex-column align-items-center">
      <h2>Contact Us</h2>
      <a href="mailto:equilibriumsports@email.com">
        <Mail /> equilibriumsports@email.com
      </a>
      <a href="tel:+1234567890">
        <Phone /> +1 (234) 567-890
      </a>
      <img src="./assets/contact-us-logo.jpg" alt="">
    </div>
  </section>
</template>
