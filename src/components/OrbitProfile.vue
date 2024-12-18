<template>
  <div class="orbit-container">
    <div class="orbit-circle">
      <div 
        v-for="(item, index) in orbitItems" 
        :key="index"
        class="orbit-item"
        :style="getPosition(index)"
      >
        <img :src="item.icon" :alt="item.name">
      </div>
    </div>
    
    <div class="profile-card">
      <div class="profile-info">
        <h2>My name is:</h2>
        <h1 class="name">Alxr</h1>
        <div class="divider"></div>
        <h3>I'm a:</h3>
        <ul class="roles">
          <li>Student</li>
          <li>operation and maintenance engineer</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const orbitItems = ref([
  { 
    name: 'Chrome', 
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/chrome/chrome-original.svg',
    orbit: 2  // 改为外圈
  },
  { 
    name: 'GitHub', 
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg',
    orbit: 1  // 中圈
  },
  { 
    name: 'Docker', 
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg',
    orbit: 2  // 外圈
  },
  { 
    name: 'Kubernetes', 
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg',
    orbit: 2  // 改为外圈
  },
  { 
    name: 'Python', 
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg',
    orbit: 1  // 中圈
  }
])

const angle = ref(0)

function getPosition(index) {
  const item = orbitItems.value[index]
  const radius = item.orbit === 1 ? 200 : 300 // 缩小半径：中圈200px，外圈300px
  const itemsInOrbit = orbitItems.value.filter(i => i.orbit === item.orbit).length
  const itemIndexInOrbit = orbitItems.value.filter((i, idx) => i.orbit === item.orbit && idx < index).length
  const itemAngle = (angle.value + (itemIndexInOrbit * (360 / itemsInOrbit))) * (Math.PI / 180)
  
  const x = Math.cos(itemAngle) * radius
  const y = Math.sin(itemAngle) * radius
  
  return {
    transform: `translate(${x}px, ${y}px)`
  }
}

onMounted(() => {
  setInterval(() => {
    angle.value = (angle.value + 0.04) % 360 // 减慢旋转速度
  }, 50)
})
</script>

<style scoped>
.orbit-container {
  position: relative;
  width: 100%;
  height: 700px; /* 减小容器高度 */
  display: flex;
  justify-content: center;
  align-items: center;
}

.orbit-circle {
  position: relative;
  width: 600px; /* 减小外圈大小 */
  height: 600px;
  border: 2px dashed rgba(0,0,0,0.1);
  border-radius: 50%;
  animation: rotate 100s linear infinite;
}

/* 只保留中圈 */
.orbit-circle::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px; /* 减小中圈大小 */
  height: 400px;
  border: 2px dashed rgba(0,0,0,0.1);
  border-radius: 50%;
  transform: translate(-50%, -50%);
}

.orbit-item {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 40px;
  height: 40px;
  margin: -20px;
  background: white;
  border-radius: 50%;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  cursor: pointer;
}

.orbit-item:hover {
  transform: scale(1.2);
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
}

.orbit-item img {
  width: 30px;
  height: 30px;
}

.profile-card {
  position: absolute;
  background: rgba(255, 255, 255, 0.95);
  padding: 2rem 3rem;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  text-align: left;
  min-width: 400px;
}

.profile-info {
  position: relative;
}

h2 {
  color: #333;
  margin: 0;
  font-size: 1.2rem;
  font-weight: normal;
}

.name {
  font-size: 3rem;
  color: #ff7f50;
  margin: 0.5rem 0;
  font-weight: bold;
  font-family: 'Segoe UI', sans-serif;
}

.divider {
  height: 1px;
  background: #ddd;
  margin: 1rem 0;
  width: 100%;
}

h3 {
  color: #333;
  margin: 1rem 0;
  font-size: 1.2rem;
  font-weight: normal;
}

.roles {
  list-style: none;
  text-align: right;
  margin: 1rem 0 0 0;
  padding: 0;
}

.roles li {
  margin: 0.3rem 0;
  color: #666;
  font-size: 1.1rem;
  line-height: 1.5;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style> 