<script setup lang="ts">
import { computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())
</script>

<template>
  <div class="app-container">
    <header class="app-header">
      <div class="header-content">
        <div class="logo">
          <router-link to="/">
            <span class="logo-icon">📊</span>
            <span class="logo-text">Kelime Sayacı</span>
          </router-link>
        </div>
        <nav class="main-nav">
          <ul>
            <li><router-link to="/" :class="{ active: $route.path === '/' }">Ana Sayfa</router-link></li>
            <li><router-link to="/about" :class="{ active: $route.path === '/about' }">Hakkında</router-link></li>
            <li><router-link to="/contact" :class="{ active: $route.path === '/contact' }">İletişim</router-link></li>
          </ul>
        </nav>
      </div>
    </header>

    <main>
      <router-view />
    </main>

    <footer class="app-footer">
      <div class="footer-content">
        <div class="footer-section">
          <h3>Kelime Sayacı</h3>
          <p>Metinlerinizi analiz etmek için kullanabileceğiniz basit ve kullanışlı bir araç.</p>
        </div>
        
        <div class="footer-section">
          <h3>Hızlı Bağlantılar</h3>
          <ul class="footer-links">
            <li><router-link to="/">Ana Sayfa</router-link></li>
            <li><router-link to="/about">Hakkında</router-link></li>
            <li><router-link to="/contact">İletişim</router-link></li>
            <li><router-link to="/privacy">Gizlilik Politikası</router-link></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h3>İletişim</h3>
          <p>
            <a href="mailto:info@kelimesayaci.com">info@kelimesayaci.com</a>
          </p>
          <div class="social-links">
            <a href="#" class="social-link">📱</a>
            <a href="#" class="social-link">📘</a>
            <a href="#" class="social-link">📸</a>
            <a href="#" class="social-link">🐦</a>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} Kelime Sayacı. Tüm hakları saklıdır.</p>
      </div>
    </footer>
  </div>
</template>

<style>
:root {
  --primary-color: #ff6b35;
  --primary-hover: #ff8659;
  --background: #f4f4f4;
  --card-bg: #ffffff;
  --text-primary: #333333;
  --text-secondary: #666666;
  --header-bg: #ffffff;
  --footer-bg: #333333;
  --footer-text: #f4f4f4;
}

body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  background: var(--background);
  font-family: 'Inter', sans-serif;
  color: var(--text-primary);
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Header Styles */
.app-header {
  background-color: var(--header-bg);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
}

.logo a {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
}

.logo-icon {
  font-size: 1.8rem;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary-color);
}

.main-nav ul {
  display: flex;
  list-style: none;
  gap: 2rem;
  padding: 0;
  margin: 0;
}

.main-nav a {
  text-decoration: none;
  color: var(--text-primary);
  font-weight: 500;
  padding: 0.5rem 0;
  position: relative;
  transition: color 0.3s ease;
}

.main-nav a:hover, .main-nav a.active {
  color: var(--primary-color);
}

.main-nav a::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--primary-color);
  transition: width 0.3s ease;
}

.main-nav a:hover::after, .main-nav a.active::after {
  width: 100%;
}

main {
  flex: 1;
}

/* Footer Styles */
.app-footer {
  background-color: var(--footer-bg);
  color: var(--footer-text);
  padding: 3rem 2rem 1rem;
  margin-top: 2rem;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.footer-section h3 {
  color: var(--primary-color);
  margin-bottom: 1.2rem;
  font-size: 1.3rem;
}

.footer-section p {
  line-height: 1.6;
  margin-bottom: 1rem;
}

.footer-links {
  list-style: none;
  padding: 0;
}

.footer-links li {
  margin-bottom: 0.8rem;
}

.footer-links a, .footer-section a {
  color: var(--footer-text);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover, .footer-section a:hover {
  color: var(--primary-color);
}

.social-links {
  display: flex;
  gap: 1rem;
  margin-top: 1rem;
}

.social-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
  font-size: 1.2rem;
}

.social-link:hover {
  background-color: var(--primary-color);
  transform: translateY(-3px);
}

.footer-bottom {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
  padding-top: 2rem;
  margin-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom p {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.7);
}

@media (max-width: 768px) {
  .header-content {
    flex-direction: column;
    padding: 1rem;
  }
  
  .logo {
    margin-bottom: 1rem;
  }
  
  .main-nav ul {
    gap: 1rem;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
  }
}
</style>
