<script setup lang="ts">
</script>

<template>
  <div class="page-container">
    <div class="page-content">
      <h1>Hakkımızda</h1>
      
      <section class="about-section">
        <h2>Kelime Sayacı Nedir?</h2>
        <p>
          Kelime Sayacı, metinlerinizi analiz etmek için tasarlanmış kullanıcı dostu bir araçtır. 
          2023 yılında kurulan platformumuz, yazarlar, öğrenciler, içerik üreticileri ve metin analizi 
          ihtiyacı olan herkes için geliştirilmiştir.
        </p>
      </section>
      
      <section class="about-section">
        <h2>Misyonumuz</h2>
        <p>
          Misyonumuz, kullanıcılarımıza metinlerini kolayca analiz edebilecekleri, 
          sade ve kullanışlı bir platform sunmaktır. Kelime sayısı, karakter sayısı, 
          paragraf sayısı gibi temel metriklerin yanı sıra, kelime yoğunluğu analizi ve 
          okuma süresi tahmini gibi gelişmiş özellikler sunarak içerik oluşturma sürecinizi 
          daha verimli hale getirmeyi amaçlıyoruz.
        </p>
      </section>
      
      <section class="about-section">
        <h2>Neden Bizi Tercih Etmelisiniz?</h2>
        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon">🚀</div>
            <h3>Hızlı ve Verimli</h3>
            <p>Anlık analiz sonuçları ile zaman kazanın.</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">🔒</div>
            <h3>Güvenli</h3>
            <p>Metinleriniz sunucularımıza kaydedilmez, tamamen gizli kalır.</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">💯</div>
            <h3>Ücretsiz</h3>
            <p>Tüm özelliklerimiz tamamen ücretsizdir.</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">📱</div>
            <h3>Mobil Uyumlu</h3>
            <p>Her cihazda sorunsuz çalışır.</p>
          </div>
        </div>
      </section>
      
      <section class="about-section">
        <h2>Ekibimiz</h2>
        <p>
          Kelime Sayacı, kullanıcı deneyimi ve yazılım geliştirme konusunda uzman 
          bir ekip tarafından geliştirilmiştir. Platformumuzu sürekli olarak iyileştirmek 
          ve yeni özellikler eklemek için çalışıyoruz.
        </p>
      </section>
    </div>
  </div>
</template>

<style scoped>
.page-container {
  display: flex;
  justify-content: center;
  padding: 2rem;
  background-color: var(--background);
}

.page-content {
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

.about-section {
  margin-bottom: 3rem;
}

.about-section p {
  line-height: 1.8;
  color: var(--text-primary);
  font-size: 1.1rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-top: 1.5rem;
}

.feature-card {
  background: #f8f8f8;
  padding: 1.5rem;
  border-radius: 16px;
  text-align: center;
  transition: all 0.3s ease;
  border: 1px solid #eee;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  border-color: var(--primary-color);
}

.feature-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.feature-card h3 {
  color: var(--primary-color);
  margin-bottom: 0.5rem;
  font-size: 1.3rem;
}

.feature-card p {
  color: var(--text-secondary);
  font-size: 1rem;
}

@media (max-width: 768px) {
  .page-container {
    padding: 1rem;
  }
  
  .page-content {
    padding: 1.5rem;
  }
  
  h1 {
    font-size: 2rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
  }
}
</style>
