<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-section">
        <h3>关于我</h3>
        <p>一个热爱技术的开发者</p>
      </div>
      
      <div class="footer-section">
        <h3>联系方式</h3>
        <div class="contact-links">
          <a href="https://github.com/286057423" target="_blank">
            <i class="fab fa-github"></i> GitHub
          </a>
          <a href="mailto:h286057423@163.com">
            <i class="fas fa-envelope"></i> Email
          </a>
        </div>
      </div>
      
      <div class="footer-section">
        <h3>技术栈</h3>
        <div class="tech-stack">
          <span>Python</span>
          <span>Ansible</span>
          <span>nginx</span>
          <span>docker</span>
          <span>kubernetes</span>
        </div>
      </div>
    </div>
    
    <div class="footer-bottom">
      <p>© 2024 Alxr. Contact me.</p>
      <div class="beian-info">
        <a href="https://beian.miit.gov.cn/" target="_blank" rel="noopener">
          陕ICP备2023006422号-1
        </a>
        <a href="http://www.beian.gov.cn/portal/registerSystemInfo" target="_blank" rel="noopener">
          <img src="https://www.beian.gov.cn/img/new/gongan.png" alt="公安备案图标"/>
          陕公网安备61040202000677
        </a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #f8f9fa;
  padding: 3rem 0 1rem;
  margin-top: 4rem;
  border-top: 1px solid #eee;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.footer-section h3 {
  color: #333;
  margin-bottom: 1rem;
  font-size: 1.2rem;
}

.footer-section p {
  color: #666;
  line-height: 1.6;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.contact-links a {
  color: #666;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-links a:hover {
  color: #ff7f50;
}

.contact-links i {
  width: 20px;
  margin-right: 0.5rem;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-stack span {
  background: #fff;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.9rem;
  color: #666;
  border: 1px solid #eee;
}

.footer-bottom {
  text-align: center;
  margin-top: 2rem;
  padding-top: 1rem;
  border-top: 1px solid #eee;
  color: #999;
  font-size: 0.9rem;
}

.beian-info {
  margin-top: 1rem;
  display: flex;
  justify-content: center;
  gap: 1rem;
  font-size: 0.9rem;
}

.beian-info a {
  color: #999;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.beian-info a:hover {
  color: #666;
}

.beian-info img {
  height: 16px;
  width: auto;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .contact-links {
    align-items: center;
  }
  
  .tech-stack {
    justify-content: center;
  }
  
  .beian-info {
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
  }
}
</style> 