<script setup lang="ts">
import { ref, computed } from 'vue'

const text = ref('')

const wordCount = computed(() => {
  return text.value.trim() ? text.value.trim().split(/\s+/).length : 0
})

const charCount = computed(() => text.value.length)
const charNoSpaces = computed(() => text.value.replace(/\s/g, '').length)
const lineCount = computed(() => text.value ? text.value.split('\n').length : 0)

const paragraphCount = computed(() => {
  if (!text.value.trim()) return 0
  return text.value.trim().split(/\n\s*\n/).filter(para => para.trim().length > 0).length
})

const readingTime = computed(() => {
  const wordsPerMinute = 200
  const minutes = Math.ceil(wordCount.value / wordsPerMinute)
  return minutes
})

const keywordDensity = computed(() => {
  if (!text.value.trim()) return []
  
  const words = text.value.toLowerCase().match(/\b\w+\b/g) || []
  const wordMap = new Map()
  
  words.forEach(word => {
    wordMap.set(word, (wordMap.get(word) || 0) + 1)
  })
  
  return Array.from(wordMap.entries())
    .map(([word, count]) => ({
      word,
      count,
      percentage: ((count as number) / words.length * 100).toFixed(1)
    }))
    .sort((a, b) => (b.count as number) - (a.count as number))
    .slice(0, 10)
})

const clearText = () => {
  text.value = ''
}
</script>

<template>
  <div class="container">
    <div class="content-wrapper">
      <h1>Kelime Sayacı</h1>
      
      <div class="stats">
        <div class="stat-box">
          <div class="stat-icon">📝</div>
          <span class="number">{{ wordCount }}</span>
          <span class="label">Kelime</span>
        </div>
        <div class="stat-box">
          <div class="stat-icon">🔤</div>
          <span class="number">{{ charCount }}</span>
          <span class="label">Karakter</span>
        </div>
        <div class="stat-box">
          <div class="stat-icon">📊</div>
          <span class="number">{{ charNoSpaces }}</span>
          <span class="label">Boşluksuz Karakter</span>
        </div>
        <div class="stat-box">
          <div class="stat-icon">📋</div>
          <span class="number">{{ lineCount }}</span>
          <span class="label">Satır</span>
        </div>
        <div class="stat-box">
          <div class="stat-icon">📑</div>
          <span class="number">{{ paragraphCount }}</span>
          <span class="label">Paragraf</span>
        </div>
        <div class="stat-box">
          <div class="stat-icon">⏱️</div>
          <span class="number">{{ readingTime }}</span>
          <span class="label">Dakika Okuma</span>
        </div>
      </div>

      <div class="textarea-container">
        <textarea
          v-model="text"
          placeholder="Metninizi buraya yazın veya yapıştırın..."
          rows="10"
        ></textarea>
        <button @click="clearText" class="clear-btn">
          <span class="btn-icon">🗑️</span>
          Temizle
        </button>
      </div>

      <div v-if="keywordDensity.length" class="keyword-density">
        <h2>Kelime Yoğunluğu Analizi</h2>
        <div class="keyword-list">
          <div v-for="item in keywordDensity" :key="item.word" class="keyword-item">
            <span class="keyword">{{ item.word }}</span>
            <div class="keyword-stats">
              <span class="keyword-count">{{ item.count }}x</span>
              <span class="keyword-percentage">{{ item.percentage }}%</span>
            </div>
          </div>
        </div>
      </div>
      
      <!-- SEO Promotional Text Section -->
      <section class="seo-promo-section">
        <h2>Ücretsiz Online Kelime Sayacı Aracı</h2>
        <div class="seo-content">
          <div class="seo-text">
            <p>
              <strong>Kelime Sayacı</strong>, metinlerinizi anında analiz eden ücretsiz bir online araçtır. 
              Makaleleriniz, ödevleriniz, blog yazılarınız veya herhangi bir metin için 
              <strong>kelime sayısı</strong>, <strong>karakter sayısı</strong>, <strong>paragraf sayısı</strong> 
              ve <strong>okuma süresi</strong> gibi önemli metrikleri saniyeler içinde öğrenin.
            </p>
            
            <p>
              SEO çalışmalarınız için <strong>kelime yoğunluğu analizi</strong> yaparak içeriğinizi optimize edin. 
              Metninizde en sık kullanılan kelimeleri ve bunların yüzdelik oranlarını görüntüleyerek, 
              anahtar kelime kullanımınızı dengeleyin ve arama motorlarında daha iyi sıralamalara ulaşın.
            </p>
            
            <p>
              <strong>Türkçe kelime sayacı</strong> aracımız, öğrenciler, yazarlar, içerik üreticileri, 
              SEO uzmanları ve metin analizi ihtiyacı olan herkes için tasarlanmıştır. 
              Kullanımı kolay arayüzü ve hızlı sonuçlarıyla, metin analizi ihtiyaçlarınız için 
              ideal çözüm sunar.
            </p>
            
            <p>
              Metinlerinizi <strong>online kelime sayma</strong> aracımızla analiz etmek için 
              hiçbir yazılım indirmenize gerek yok. Tamamen ücretsiz olan bu hizmet, 
              tarayıcınız üzerinden anında erişilebilir ve kullanılabilir.
            </p>
          </div>
          
          <div class="seo-features">
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Anında kelime sayımı</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Karakter sayısı hesaplama</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Paragraf sayısı analizi</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Kelime yoğunluğu ölçümü</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Okuma süresi tahmini</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Tamamen ücretsiz</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Gizlilik koruması</span>
            </div>
            <div class="seo-feature-item">
              <div class="feature-icon">✓</div>
              <span>Kullanımı kolay arayüz</span>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
}

.content-wrapper {
  width: 100%;
  max-width: 900px;
  background: var(--card-bg);
  border-radius: 24px;
  padding: 2.5rem;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
}

h1 {
  text-align: center;
  margin-bottom: 2.5rem;
  font-size: 2.8rem;
  font-weight: 700;
  color: var(--primary-color);
}

h2 {
  color: var(--primary-color);
  margin: 2rem 0 1rem;
  font-size: 1.8rem;
}

.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2.5rem;
}

.stat-box {
  background: var(--card-bg);
  padding: 1.5rem;
  border-radius: 16px;
  text-align: center;
  transition: all 0.3s ease;
  border: 2px solid var(--primary-color);
}

.stat-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(255, 107, 53, 0.2);
}

.stat-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.number {
  display: block;
  font-size: 2.2rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: var(--primary-color);
}

.label {
  font-size: 1rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.textarea-container {
  position: relative;
  margin-top: 2rem;
}

textarea {
  width: 100%;
  padding: 1.5rem;
  border-radius: 16px;
  border: 2px solid #e0e0e0;
  background: var(--card-bg);
  color: var(--text-primary);
  font-size: 1.1rem;
  resize: vertical;
  min-height: 200px;
  transition: all 0.3s ease;
  line-height: 1.6;
}

textarea:focus {
  outline: none;
  border-color: var(--primary-color);
  box-shadow: 0 0 20px rgba(255, 107, 53, 0.1);
}

textarea::placeholder {
  color: var(--text-secondary);
}

.clear-btn {
  position: absolute;
  bottom: 1.5rem;
  right: 1.5rem;
  padding: 0.8rem 1.5rem;
  border: none;
  border-radius: 12px;
  background: var(--primary-color);
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1rem;
  font-weight: 500;
}

.clear-btn:hover {
  background: var(--primary-hover);
  transform: translateY(-2px);
}

.btn-icon {
  font-size: 1.2rem;
}

.keyword-density {
  margin-top: 2.5rem;
  padding-top: 2rem;
  border-top: 2px solid #eee;
}

.keyword-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
}

.keyword-item {
  background: #f8f8f8;
  padding: 1rem;
  border-radius: 12px;
  border: 1px solid #eee;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: all 0.3s ease;
}

.keyword-item:hover {
  border-color: var(--primary-color);
  transform: translateX(5px);
}

.keyword {
  font-weight: 500;
  color: var(--text-primary);
}

.keyword-stats {
  display: flex;
  gap: 1rem;
  color: var(--text-secondary);
}

.keyword-count {
  color: var(--primary-color);
  font-weight: 600;
}

.keyword-percentage {
  color: var(--text-secondary);
  font-size: 0.9rem;
}

/* SEO Promotional Section Styles */
.seo-promo-section {
  margin-top: 3rem;
  padding-top: 2rem;
  border-top: 2px solid #eee;
}

.seo-promo-section h2 {
  text-align: center;
  margin-bottom: 1.5rem;
}

.seo-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
}

.seo-text p {
  margin-bottom: 1rem;
  line-height: 1.8;
  color: var(--text-primary);
  font-size: 1.05rem;
}

.seo-text strong {
  color: var(--primary-color);
  font-weight: 600;
}

.seo-features {
  background: #f8f8f8;
  padding: 1.5rem;
  border-radius: 16px;
  border: 1px solid #eee;
}

.seo-feature-item {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 1px dashed #e0e0e0;
}

.seo-feature-item:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}

.feature-icon {
  color: var(--primary-color);
  font-weight: bold;
  font-size: 1.2rem;
}

@media (max-width: 768px) {
  .container {
    padding: 1rem;
  }
  
  .content-wrapper {
    padding: 1.5rem;
  }
  
  h1 {
    font-size: 2rem;
  }
  
  .stats {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
  }
  
  .number {
    font-size: 1.8rem;
  }

  .keyword-list {
    grid-template-columns: 1fr;
  }
  
  .seo-content {
    grid-template-columns: 1fr;
  }
  
  .seo-features {
    margin-top: 1rem;
  }
}
</style>
