<template>
  <div class="section-content">
    <h2 class="section-title">游戏</h2>
    <div class="games-grid">
      <div class="game-card" v-for="game in games" :key="game.name">
        <div class="game-info">
          <div class="game-header">
            <h3>{{ game.name }}</h3>
            <div class="game-rating">
              <i class="fas fa-star"></i>
              <span>{{ game.rating }}/10</span>
            </div>
          </div>
          <p class="game-description">{{ game.description }}</p>
          <div class="game-tags">
            <span v-for="tag in game.tags" :key="tag">{{ tag }}</span>
          </div>
          <a :href="game.link" target="_blank" class="game-link">
            <i class="fas fa-external-link-alt"></i> 访问官网
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const games = [
  {
    name: "Minecraft",
    description: "一个关于放置方块和冒险的游戏，在这里你可以创造属于自己的世界",
    rating: 9.5,
    tags: ["沙盒", "生存", "建造", "多人联机"],
    link: "https://www.minecraft.net/"
  },
  {
    name: "原神",
    description: "探索广阔的提瓦特大陆，邂逅性格各异的同伴，在旅途中邂逅各种奇遇",
    rating: 9.0,
    tags: ["开放世界", "角色扮演", "冒险"],
    link: "https://ys.mihoyo.com/"
  }
]
</script>

<style scoped>
.games-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.game-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.game-card:hover {
  transform: translateY(-5px);
}

.game-info {
  padding: 1.5rem;
}

.game-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.game-header h3 {
  color: #333;
  font-size: 1.3rem;
  margin: 0;
}

.game-rating {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #ffd700;
  font-weight: 500;
}

.game-rating span {
  color: #666;
}

.game-description {
  color: #666;
  margin-bottom: 1.5rem;
  line-height: 1.5;
}

.game-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.game-tags span {
  background: #f5f5f5;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.9rem;
  color: #666;
}

.game-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 500;
  margin-top: 1rem;
  transition: color 0.3s ease;
}

.game-link:hover {
  text-decoration: underline;
}

.game-info {
  display: flex;
  flex-direction: column;
}

.game-tags {
  margin-bottom: auto;
}
</style> 