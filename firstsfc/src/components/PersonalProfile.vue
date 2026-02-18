<template>
  <div class="dashboard-container">
    <aside class="sidebar">
      <div class="profile-section">
        <img 
          src="https://i.pinimg.com/1200x/21/7c/94/217c941f96d0457074411d1896d3625a.jpg" 
          alt="Daniel Whitwell" 
          class="avatar"
        >
        <h2>Daniel Whitwell</h2>
        <p class="subtitle">Cybersecurity Student</p>
      </div>
      
      <nav class="nav-menu">
        <a href="#about" class="nav-item">About Me</a>
        <a href="#education" class="nav-item">Education</a>
        <a href="#it-experience" class="nav-item">IT Experience</a>
        <a href="#hobbies" class="nav-item">Hobbies</a>
        <a href="#comments" class="nav-item">Guestbook</a>
      </nav>
    </aside>

    <main class="main-content">
      <header class="content-header">
        <h1>Personal Profile</h1>
      </header>

      <div class="grid-layout">
        <section id="about" class="card main-bio">
          <h3>About Me</h3>
          <p>
            Hello! I'm Daniel Whitwell, currently studying a Bachelor of Science in 
            Computer Science specializing in <strong>Cybersecurity & Forensics</strong> 
            at Asia Pacific College.
          </p>
          <div class="details-grid">
            <div class="detail-item">
              <strong>Education:</strong> Graduated GE Track (SHS)
            </div>
            <div class="detail-item">
              <strong>Goal:</strong> To excel in the IT industry and build a successful future.
            </div>
          </div>
        </section>

        <section class="card facts-card">
          <h3>Quick Facts</h3>
          <ul>
            <li>🎮 Passionate Gamer</li>
            <li>📺 Anime Enthusiast</li>
            <li>🛡️ Cybersec Aspirant</li>
            <li>💻 Java & Python Coder</li>
          </ul>
        </section>

        <section id="it-experience" class="card experience-card">
          <h3>Technical Skills</h3>
          <div class="tags">
            <span class="tag">Java</span>
            <span class="tag">Python</span>
            <span class="tag">HTML/CSS</span>
            <span class="tag">Kali Linux</span>
            <span class="tag">SQL</span>
            <span class="tag">Vue.js</span>
          </div>
        </section>

        <section id="comments" class="card comment-section">
          <h3>Guestbook</h3>
          <p>Leave a message below!</p>
          <form @submit.prevent="handleCommentSubmit" class="comment-form">
            <input v-model="form.name" type="text" placeholder="Your Name" required />
            <textarea v-model="form.comment" placeholder="Write a comment..." required></textarea>
            <button type="submit" :disabled="loading">
              {{ loading ? 'Sending...' : 'Post Comment' }}
            </button>
          </form>
        </section>
      </div>
    </main>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
// import { supabase } from '../supabase' // Uncomment when your supabase.js is ready

const loading = ref(false)
const form = reactive({
  name: '',
  comment: ''
})

const handleCommentSubmit = async () => {
  loading.value = true
  // Insert Supabase logic here
  console.log("Form Submitted:", form)
  setTimeout(() => {
    loading.value = false
    alert("Message sent! (Backend connection pending)")
    form.name = ''
    form.comment = ''
  }, 1000)
}
</script>

<style scoped>
:root {
  --primary: #6366f1;
  --bg: #f8fafc;
  --text: #1e293b;
  --card-bg: #ffffff;
}

.dashboard-container {
  display: flex;
  min-height: 100vh;
  background-color: #f1f5f9;
  font-family: 'Inter', sans-serif;
  color: #1e293b;
}

/* Sidebar */
.sidebar {
  width: 280px;
  background: #1e293b;
  color: white;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  position: fixed;
  height: 100vh;
}

.profile-section {
  text-align: center;
  margin-bottom: 2rem;
}

.avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 3px solid #6366f1;
  margin-bottom: 1rem;
  object-fit: cover;
}

.nav-menu {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.nav-item {
  color: #94a3b8;
  text-decoration: none;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  transition: all 0.2s;
}

.nav-item:hover {
  background: #334155;
  color: white;
}

/* Main Content */
.main-content {
  margin-left: 280px;
  flex: 1;
  padding: 2rem;
}

.grid-layout {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 1.5rem;
}

.card {
  background: white;
  padding: 1.5rem;
  border-radius: 12px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
}

.main-bio { grid-column: span 1; }

/* Comment Form Styling */
.comment-form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 15px;
}

.comment-form input, .comment-form textarea {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 6px;
}

.comment-form button {
  background: #6366f1;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 6px;
  cursor: pointer;
}

.tags { display: flex; flex-wrap: wrap; gap: 8px; }
.tag { background: #e2e8f0; padding: 4px 12px; border-radius: 20px; font-size: 0.85rem; }

/* Responsive */
@media (max-width: 1024px) {
  .sidebar { width: 80px; padding: 1rem; }
  .sidebar h2, .sidebar p, .nav-item { display: none; }
  .main-content { margin-left: 80px; }
  .grid-layout { grid-template-columns: 1fr; }
}
</style>
