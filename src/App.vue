<template>
  <div class="app">
    <Header />
    <main class="main">
      <OrbitProfile />
      <section id="favorites" class="section">
        <FavoritesSection />
      </section>
      <section id="code" class="section">
        <CodeSection />
      </section>
      <section id="game" class="section">
        <GameSection />
      </section>
      <section id="books" class="section">
        <BooksSection />
      </section>
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import OrbitProfile from './components/OrbitProfile.vue'
import Footer from './components/Footer.vue'
import FavoritesSection from './components/sections/FavoritesSection.vue'
import CodeSection from './components/sections/CodeSection.vue'
import GameSection from './components/sections/GameSection.vue'
import BooksSection from './components/sections/BooksSection.vue'
</script>

<style>
:root {
  --primary-color: #ff7f50;
  --text-color: #333;
  --bg-color: #f5f5f5;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 
    Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color: var(--text-color);
  background: var(--bg-color);
}

.app {
  min-height: 100vh;
}

.main {
  margin-top: 80px; /* Header height + padding */
  padding: 2rem;
  min-height: calc(100vh - 200px); /* 确保主内容区域有足够的高度 */
}

@media (max-width: 768px) {
  .main {
    margin-top: 140px;
    padding: 1rem;
  }
}

/* 添加一些全局动画 */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  animation: fadeIn 0.5s ease-out forwards;
}

.section {
  padding: 4rem 0;
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  font-size: 2rem;
  color: #333;
  margin-bottom: 2rem;
  text-align: center;
}

.section-content {
  padding: 0 2rem;
}
</style> 