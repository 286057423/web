<template>
  <div class="section-content">
    <h2 class="section-title">代码</h2>
    <div class="code-projects">
      <div class="project-card" v-for="project in projects" :key="project.name">
        <h3>{{ project.name }}</h3>
        <p>{{ project.description }}</p>
        <div class="project-tech">
          <span v-for="tech in project.technologies" :key="tech">{{ tech }}</span>
        </div>
        <a :href="project.link" target="_blank" class="project-link">
          <i class="fab fa-github"></i> 查看项目
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
const projects = [
  {
    name: "项目名称",
    description: "Ansible一键部署keepalived+nginx高可用高并发平台",
    technologies: ["Ansible", "keepalived", "nginx"],
    link: "https://github.com/286057423/items"
  },
  // 更多项目...
  {
    name: "项目名称",
    description: "利用Docker部署LNMP环境的wordpress博客",
    technologies: ["Docker", "LNMP", "wordpress"],
    link: "https://github.com/286057423/items"
  }
]
</script>

<style scoped>
.code-projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card {
  background: white;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.1);
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin: 1rem 0;
}

.project-tech span {
  background: #f5f5f5;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.9rem;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: #ff7f50;
  text-decoration: none;
}

.project-link:hover {
  text-decoration: underline;
}
</style> 