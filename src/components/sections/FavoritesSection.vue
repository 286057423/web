<template>
  <div class="section-content">
    <h2 class="section-title">收藏</h2>
    <div class="favorites-grid">
      <div class="favorite-card" v-for="item in favorites" :key="item.name">
        <div class="favorite-info">
          <h3>{{ item.name }}</h3>
          <p>{{ item.description }}</p>
          <a :href="item.link" target="_blank" class="favorite-link">
            <i class="fas fa-external-link-alt"></i> 了解更多
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const favorites = [
  {
    name: "Linux",
    description: "开源操作系统内核",
    link: "https://www.linux.org/"
  },
  {
    name: "Python",
    description: "简单易学的编程语言",
    link: "https://www.python.org/"
  },
  {
    name: "Docker",
    description: "容器化平台",
    link: "https://www.docker.com/"
  },
  {
    name: "阿里开源镜像站",
    description: "阿里开源镜像站",
    link: "https://developer.aliyun.com/mirror/"
  },
  {
    name: "清华开源镜像站",
    description: "清华开源镜像站",
    link: "https://mirrors.tuna.tsinghua.edu.cn/"
  },
  {
    name: "华为开源镜像站",
    description: "华为开源镜像站",
    link: "https://mirrors.huaweicloud.com/"
  }
]
</script>

<style scoped>
.favorites-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.favorite-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.favorite-card:hover {
  transform: translateY(-5px);
}

.favorite-info {
  padding: 1.5rem;
}

.favorite-info h3 {
  color: #333;
  font-size: 1.3rem;
  margin-bottom: 1rem;
}

.favorite-info p {
  color: #666;
  margin-bottom: 1.5rem;
  line-height: 1.5;
}

.favorite-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 500;
}

.favorite-link:hover {
  text-decoration: underline;
}
</style> 