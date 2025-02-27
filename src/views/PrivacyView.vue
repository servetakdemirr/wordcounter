<script setup lang="ts">
</script>

<template>
  <div class="page-container">
    <div class="page-content">
      <h1>Gizlilik Politikası</h1>
      
      <div class="last-updated">
        <p>Son Güncelleme: 1 Haziran 2023</p>
      </div>
      
      <section class="policy-section">
        <h2>1. Giriş</h2>
        <p>
          Kelime Sayacı olarak gizliliğinize saygı duyuyoruz. Bu Gizlilik Politikası, 
          web sitemizi kullanırken bilgilerinizin nasıl toplandığını, kullanıldığını ve 
          korunduğunu açıklamaktadır. Sitemizi kullanarak, bu politikada belirtilen 
          uygulamaları kabul etmiş olursunuz.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>2. Toplanan Bilgiler</h2>
        <p>
          <strong>Kelime Sayacı, metinlerinizi sunucularımıza kaydetmez veya saklamaz.</strong> 
          Tüm metin analizi işlemleri tarayıcınızda gerçekleştirilir ve verileriniz cihazınızdan 
          ayrılmaz.
        </p>
        <p>
          Ancak, sitemizi ziyaret ettiğinizde aşağıdaki bilgiler otomatik olarak toplanabilir:
        </p>
        <ul>
          <li>IP adresi</li>
          <li>Tarayıcı türü ve versiyonu</li>
          <li>Ziyaret tarihi ve saati</li>
          <li>Ziyaret edilen sayfalar</li>
          <li>Yönlendiren web sitesi</li>
        </ul>
        <p>
          Bu bilgiler, hizmetlerimizi iyileştirmek, site kullanımını analiz etmek ve 
          güvenliği sağlamak amacıyla kullanılır.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>3. Çerezler</h2>
        <p>
          Sitemiz, deneyiminizi geliştirmek için çerezleri kullanabilir. Çerezler, 
          tarayıcınız tarafından cihazınıza yerleştirilen küçük metin dosyalarıdır. 
          Çerezleri kabul etmek zorunda değilsiniz ve tarayıcı ayarlarınızdan çerezleri 
          reddedebilirsiniz, ancak bu durumda sitemizin bazı özellikleri düzgün çalışmayabilir.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>4. Üçüncü Taraf Hizmetleri</h2>
        <p>
          Sitemiz, aşağıdaki üçüncü taraf hizmetlerini kullanabilir:
        </p>
        <ul>
          <li>Google Analytics: Site trafiğini analiz etmek için</li>
          <li>Sosyal medya butonları: İçeriği paylaşmanızı sağlamak için</li>
        </ul>
        <p>
          Bu hizmetler kendi çerezlerini kullanabilir ve kendi gizlilik politikalarına 
          sahiptir. Bu hizmetlerin gizlilik uygulamaları hakkında daha fazla bilgi için 
          ilgili gizlilik politikalarını incelemenizi öneririz.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>5. Veri Güvenliği</h2>
        <p>
          Bilgilerinizin güvenliğini sağlamak için uygun teknik ve organizasyonel önlemleri 
          alıyoruz. Ancak, internet üzerinden veri iletiminin %100 güvenli olmadığını 
          unutmayın.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>6. Haklarınız</h2>
        <p>
          Kişisel verilerinizle ilgili olarak aşağıdaki haklara sahipsiniz:
        </p>
        <ul>
          <li>Verilerinize erişim talep etme hakkı</li>
          <li>Verilerinizin düzeltilmesini talep etme hakkı</li>
          <li>Verilerinizin silinmesini talep etme hakkı</li>
          <li>Veri işlemeye itiraz etme hakkı</li>
          <li>Veri taşınabilirliği hakkı</li>
        </ul>
        <p>
          Bu haklarınızı kullanmak için lütfen bizimle iletişime geçin.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>7. Politika Değişiklikleri</h2>
        <p>
          Bu Gizlilik Politikası'nı zaman zaman güncelleyebiliriz. Değişiklikler 
          yapıldığında, bu sayfada güncellenmiş politikayı yayınlayacağız ve 
          güncelleme tarihini değiştireceğiz.
        </p>
      </section>
      
      <section class="policy-section">
        <h2>8. İletişim</h2>
        <p>
          Bu Gizlilik Politikası hakkında sorularınız veya endişeleriniz varsa, 
          lütfen <a href="mailto:info@kelimesayaci.com">info@kelimesayaci.com</a> 
          adresinden bizimle iletişime geçin.
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
  margin-bottom: 1.5rem;
  font-size: 2.8rem;
  font-weight: 700;
  color: var(--primary-color);
}

.last-updated {
  text-align: center;
  margin-bottom: 2.5rem;
  color: var(--text-secondary);
  font-style: italic;
}

h2 {
  color: var(--primary-color);
  margin: 2rem 0 1rem;
  font-size: 1.5rem;
}

.policy-section {
  margin-bottom: 2.5rem;
}

.policy-section p, .policy-section li {
  line-height: 1.8;
  color: var(--text-primary);
  font-size: 1.1rem;
  margin-bottom: 1rem;
}

.policy-section ul {
  padding-left: 2rem;
  margin-bottom: 1.5rem;
}

.policy-section a {
  color: var(--primary-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.policy-section a:hover {
  color: var(--primary-hover);
  text-decoration: underline;
}

strong {
  font-weight: 600;
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
}
</style>
