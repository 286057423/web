<template>
  <header class="header">
    <div class="logo">
      <span>Alxr</span>
    </div>
    
    <nav class="nav">
      <a 
        v-for="item in menuItems" 
        :key="item.name"
        :href="item.href"
        :class="{ active: currentSection === item.name }"
        @click="setCurrentSection(item.name)"
      >
        {{ item.label }}
      </a>
    </nav>
    
    <div class="social">
      <a v-for="item in socialLinks" 
         :key="item.name" 
         :href="item.url" 
         :title="item.name"
         target="_blank"
         rel="noopener noreferrer"
      >
        <i :class="item.icon"></i>
      </a>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const currentSection = ref('首页')

const menuItems = [
  { name: 'favorites', label: '收藏', href: '#favorites' },
  { name: 'code', label: '代码', href: '#code' },
  { name: 'game', label: '游戏', href: '#game' },
  { name: 'books', label: '书籍', href: '#books' }
]

const socialLinks = [
  { name: 'GitHub', url: 'https://github.com/286057423', icon: 'fab fa-github' },
  { name: '邮箱', url: 'mailto:h286057423@163.com', icon: 'fas fa-envelope' }
]

const setCurrentSection = (section) => {
  currentSection.value = section
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.5rem;
  font-weight: bold;
}

.logo img {
  height: 32px;
  width: auto;
}

.nav {
  display: flex;
  gap: 2rem;
}

.nav a {
  text-decoration: none;
  color: #666;
  font-weight: 500;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: all 0.3s ease;
}

.nav a:hover {
  color: #333;
  background: rgba(0,0,0,0.05);
}

.nav a.active {
  color: #ff7f50;
  background: rgba(255,127,80,0.1);
}

.social {
  display: flex;
  gap: 1rem;
}

.social a {
  color: #666;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}

.social a:hover {
  color: #ff7f50;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .header {
    flex-direction: column;
    padding: 1rem;
  }
  
  .nav {
    margin: 1rem 0;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
  }
  
  .social {
    margin-top: 1rem;
  }
}
</style> 