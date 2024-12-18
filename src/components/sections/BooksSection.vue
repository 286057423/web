<template>
  <div class="section-content">
    <h2 class="section-title">书籍</h2>
    <div class="books-grid">
      <div class="book-card" v-for="book in books" :key="book.name">
        <div class="book-info">
          <h3>{{ book.name }}</h3>
          <p class="book-author">{{ book.author }}</p>
          <p class="book-description">{{ book.description }}</p>
          <div class="book-footer">
            <div class="book-rating">
              <i class="fas fa-star"></i>
              <span>{{ book.rating }}/5</span>
            </div>
            <a :href="book.link" target="_blank" class="book-link">
              <i class="fas fa-external-link-alt"></i> 阅读详情
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const books = [
  {
    name: "计算机网络：自顶向下方法",
    author: "James F. Kurose / Keith W. Ross",
    description: "计算机网络领域的经典教材，采用自顶向下的方法讲解网络原理，深入浅出",
    rating: 4.9,
    link: "https://book.douban.com/subject/26176870/"
  },
  {
    name: "剑来",
    author: "烽火戏诸侯",
    description: "大千世界，无奇不有。我陈平安，唯有一剑，可搬山，倒海，降妖，镇魔，敕神，摘星，断江，摧城，开天！",
    rating: 4.7,
    link: "https://m.xbiqugex.cc/book_67088/"
  },
  {
    name: "算法导论",
    author: "Thomas H. Cormen 等",
    description: "全面介绍算法和数据结构的经典著作，被誉为算法领域的圣经",
    rating: 4.8,
    link: "https://book.douban.com/subject/20432061/"
  },
  {
    name: "数据结构与算法分析：C语言描述",
    author: "Mark Allen Weiss",
    description: "系统讲解数据结构与算法分析的经典教材，以C语言为载体",
    rating: 4.7,
    link: "https://book.douban.com/subject/1139426/"
  }
]
</script>

<style scoped>
.books-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  padding: 0 1rem;
}

.book-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.book-card:hover {
  transform: translateY(-5px);
}

.book-info {
  padding: 1.5rem;
}

.book-info h3 {
  color: #333;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
}

.book-author {
  color: #666;
  font-style: italic;
  margin: 0.5rem 0;
  font-size: 1rem;
}

.book-description {
  color: #666;
  margin: 1rem 0;
  line-height: 1.5;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.book-rating {
  color: #ffd700;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-top: 1rem;
}

.book-rating span {
  color: #666;
}

.book-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid #eee;
}

.book-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.book-link:hover {
  transform: translateX(5px);
  text-decoration: underline;
}

.book-card {
  cursor: pointer;
}

.book-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 20px rgba(0,0,0,0.15);
}
</style> 