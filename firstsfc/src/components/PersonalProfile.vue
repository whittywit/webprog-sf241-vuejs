<template>
  <div class="grid-container">
    <header class="header">
      <h1>Personal Profile Web Page - Daniel Whitwell</h1>
    </header>

    <nav class="menu">
      <ul>
        <li>About me</li>
        <li>Education/Achievements</li>
        <li>Course</li>
        <li>Hobbies & Interests</li>
        <li>Goals in Life</li>
        <li>IT Experience</li>
      </ul>
    </nav>

    <main class="content">
      <h1>About me</h1>
      
      <div class="profile-pic-container">
        <img 
          src="https://i.pinimg.com/1200x/21/7c/94/217c941f96d0457074411d1896d3625a.jpg" 
          alt="Profile Picture" 
          class="profile-img"
        >
      </div>

      <div class="bio">
        <p><strong>About Me:</strong> Hello! My name is Daniel Whitwell, and I'm excited to be starting this course. I am currently studying a Bachelor of Science in Computer Science Specializing in Cybersecurity & Forensics.</p>
        <p><strong>Education / Achievements:</strong> Graduated from GE in Senior High School (General Education track).</p>
        <p><strong>IT Experience:</strong> Basic skills in Java, Python, HTML, CSS and KALI.</p>
        <p><strong>Hobbies & Interests:</strong> Watching anime, Playing all sorts of video games, and Listening to music.</p>
        <p><strong>Goals In Life / Dream:</strong> Make money and make the love of my life the happiest girl in the world.</p>
      </div>
    </main>

    <aside class="facts">
      <h2>Facts:</h2>
      <ul>
        <li>I love Anime</li>
        <li>Cybersecurity Student</li>
        <li>Gamer</li>
      </ul>
    </aside>

    <footer class="footer">
      <p>Resize the browser window to see the responsive effect.</p>
    </footer>
  </div>
</template>

<script setup>
// No logic needed yet, but the tag must exist or be empty
</script>

<style scoped>
/* Paste the content of your personalprofile.css here */
* {
  box-sizing: border-box;
}

.grid-container {
  display: grid;
  grid-template-areas:
    'header'
    'menu'
    'main'
    'facts'
    'footer';
  background-color: white;
  gap: 10px;  
}

.header {
  grid-area: header;
  background-color: #960086; /* Your purple */
  text-align: center;
  color: #ffffff;
  padding: 10px;
}

.menu {
  grid-area: menu;
}

.menu ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.menu li {
  padding: 8px;
  margin-bottom: 7px;
  background-color: #33b5e5;
  color: #ffffff;
}

.content {
  grid-area: main;
  padding: 10px;
}

.profile-img {
  width: 250px;
  height: auto;
  border: 1px solid #ccc;
  margin-bottom: 15px;
}

.facts {
  grid-area: facts;
  border: 1px solid #0099cc;
  background-color: beige;
  padding: 10px;
}

.footer {
  grid-area: footer;
  background-color: #0099cc;
  color: #ffffff;
  text-align: center;
  padding: 5px;
}

/* Responsive Breakpoints */
@media (min-width: 600px) {
  .grid-container {
    grid-template-areas:
      'header header header header header header'
      'menu main main main main main'
      'facts facts facts facts facts facts'
      'footer footer footer footer footer footer';
  }
}

@media (min-width: 768px) {
  .grid-container {
    grid-template-areas:
      'header header header header header header'
      'menu main main main main facts'
      'footer footer footer footer footer footer';
  }
}
</style>
