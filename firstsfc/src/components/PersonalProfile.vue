<template>
  <div class="profile-wrapper">
    <header class="hero-section">
      <div class="container">
        <img 
          src="https://i.pinimg.com/1200x/21/7c/94/217c941f96d0457074411d1896d3625a.jpg" 
          alt="Daniel Whitwell" 
          class="profile-pic"
        >
        <h1>Daniel Whitwell</h1>
        <p class="tagline">Cybersecurity Student @ Asia Pacific College</p>
      </div>
    </header>

    <main class="container">
      <section class="content-card">
        <h2>About Me</h2>
        <p>
          Hello! I'm Daniel Whitwell. I am currently pursuing a Bachelor of Science in 
          Computer Science, specializing in <strong>Cybersecurity & Forensics</strong>. 
          I’m passionate about protecting digital landscapes and exploring the depths of IT security.
        </p>
      </section>

      <div class="two-col-grid">
        <section class="content-card">
          <h2>Education</h2>
          <ul class="styled-list">
            <li><strong>Degree:</strong> BS Computer Science (Cybersecurity)</li>
            <li><strong>High School:</strong> GE Track Graduate</li>
          </ul>
        </section>

        <section class="content-card">
          <h2>IT Experience</h2>
          <div class="skill-tags">
            <span class="tag">Java</span>
            <span class="tag">Python</span>
            <span class="tag">HTML/CSS</span>
            <span class="tag">Kali Linux</span>
            <span class="tag">SQL</span>
          </div>
        </section>
      </div>

      <section class="content-card">
        <h2>Interests & Facts</h2>
        <div class="interests-flex">
          <div class="interest-item">🎮 Gaming</div>
          <div class="interest-item">📺 Anime</div>
          <div class="interest-item">🎵 Music</div>
          <div class="interest-item">🛡️ Ethical Hacking</div>
        </div>
      </section>

      <section id="comments" class="content-card guestbook">
        <h2>Guestbook</h2>
        <p>Leave a message to say hello!</p>
        <form @submit.prevent="handleCommentSubmit" class="comment-form">
          <div class="form-group">
            <input v-model="form.name" type="text" placeholder="Your Name" required />
          </div>
          <div class="form-group">
            <textarea v-model="form.comment" placeholder="Your Message..." rows="3" required></textarea>
          </div>
          <button type="submit" :disabled="loading" class="submit-btn">
            {{ loading ? 'Posting...' : 'Send Message' }}
          </button>
        </form>
      </section>
    </main>

    <footer class="site-footer">
      <p>&copy; 2026 Daniel Whitwell | Built with Vue.js & Supabase</p>
    </footer>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
// import { supabase } from '../supabase' // Uncomment when ready

const loading = ref(false)
const form = reactive({
  name: '',
  comment: ''
})

const handleCommentSubmit = async () => {
  loading.value = true
  // Insert Supabase logic here
  setTimeout(() => {
    loading.value = false
    alert("Comment received! (Supabase connection pending)")
    form.name = ''
    form.comment = ''
  }, 800)
}
</script>

<style scoped>
/* Base Styles */
.profile-wrapper {
  font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #f4f7f9;
  min-height: 100vh;
  margin: 0;
  padding-bottom: 40px;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Hero Header */
.hero-section {
  background: linear-gradient(135deg, #1e293b 0%, #334155 100%);
  color: white;
  text-align: center;
  padding: 60px 0;
  margin-bottom: 40px;
}

.profile-pic {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  border: 4px solid #6366f1;
  object-fit: cover;
  margin-bottom: 20px;
}

.tagline {
  font-size: 1.2rem;
  opacity: 0.9;
}

/* Cards */
.content-card {
  background: white;
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 24px;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.content-card h2 {
  margin-top: 0;
  color: #1e293b;
  border-bottom: 2px solid #e2e8f0;
  padding-bottom: 10px;
  margin-bottom: 20px;
}

/* Grid & Layout Helpers */
.two-col-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag {
  background: #6366f1;
  color: white;
  padding: 5px 15px;
  border-radius: 20px;
  font-size: 0.9rem;
}

.interests-flex {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 15px;
}

.interest-item {
  background: #f1f5f9;
  padding: 10px 20px;
  border-radius: 8px;
  font-weight: 600;
}

/* Form Styles */
.comment-form .form-group {
  margin-bottom: 15px;
}

.comment-form input, 
.comment-form textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  font-size: 1rem;
}

.submit-btn {
  background: #6366f1;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  width: 100%;
  transition: background 0.2s;
}

.submit-btn:hover {
  background: #4f46e5;
}

.site-footer {
  text-align: center;
  font-size: 0.9rem;
  color: #64748b;
  margin-top: 40px;
}

/* Responsive */
@media (max-width: 600px) {
  .two-col-grid {
    grid-template-columns: 1fr;
  }
}
</style>
