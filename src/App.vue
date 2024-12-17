<template>
  <div class="app">
    <Header />
    <main class="main">
      <OrbitProfile />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import OrbitProfile from './components/OrbitProfile.vue'
import Footer from './components/Footer.vue'
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
</style> 