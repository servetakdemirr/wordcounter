<script setup lang="ts">
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const subject = ref('')
const message = ref('')
const submitted = ref(false)
const error = ref(false)

const submitForm = () => {
  if (name.value && email.value && message.value) {
    // In a real application, you would send the form data to a server
    console.log('Form submitted:', { name: name.value, email: email.value, subject: subject.value, message: message.value })
    submitted.value = true
    error.value = false
    
    // Reset form
    name.value = ''
    email.value = ''
    subject.value = ''
    message.value = ''
  } else {
    error.value = true
  }
}
</script>

<template>
  <div class="page-container">
    <div class="page-content">
      <h1>İletişim</h1>
      
      <div class="contact-container">
        <div class="contact-info">
          <h2>Bize Ulaşın</h2>
          <p>
            Sorularınız, önerileriniz veya geri bildirimleriniz için bizimle iletişime geçebilirsiniz.
            Aşağıdaki iletişim formunu doldurarak veya e-posta adresimiz üzerinden bize ulaşabilirsiniz.
          </p>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">✉️</div>
              <div class="method-details">
                <h3>E-posta</h3>
                <p><a href="mailto:info@kelimesayaci.com">info@kelimesayaci.com</a></p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">🌐</div>
              <div class="method-details">
                <h3>Sosyal Medya</h3>
                <div class="social-links">
                  <a href="#" class="social-link">📱</a>
                  <a href="#" class="social-link">📘</a>
                  <a href="#" class="social-link">📸</a>
                  <a href="#" class="social-link">🐦</a>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="contact-form">
          <h2>İletişim Formu</h2>
          
          <div v-if="submitted" class="form-success">
            <p>Mesajınız başarıyla gönderildi. En kısa sürede size dönüş yapacağız.</p>
          </div>
          
          <form v-else @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Adınız *</label>
              <input 
                type="text" 
                id="name" 
                v-model="name" 
                :class="{ 'error-input': error && !name }"
                required
              >
            </div>
            
            <div class="form-group">
              <label for="email">E-posta Adresiniz *</label>
              <input 
                type="email" 
                id="email" 
                v-model="email" 
                :class="{ 'error-input': error && !email }"
                required
              >
            </div>
            
            <div class="form-group">
              <label for="subject">Konu</label>
              <input type="text" id="subject" v-model="subject">
            </div>
            
            <div class="form-group">
              <label for="message">Mesajınız *</label>
              <textarea 
                id="message" 
                v-model="message" 
                rows="5" 
                :class="{ 'error-input': error && !message }"
                required
              ></textarea>
            </div>
            
            <div v-if="error" class="error-message">
              <p>Lütfen tüm zorunlu alanları doldurun.</p>
            </div>
            
            <button type="submit" class="submit-btn">
              <span class="btn-icon">📤</span>
              Gönder
            </button>
          </form>
        </div>
      </div>
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
  margin-bottom: 1.5rem;
  font-size: 1.8rem;
}

.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
}

.contact-info p {
  line-height: 1.8;
  color: var(--text-primary);
  font-size: 1.1rem;
  margin-bottom: 2rem;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.method-icon {
  font-size: 2rem;
  color: var(--primary-color);
}

.method-details h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1.2rem;
  color: var(--text-primary);
}

.method-details p {
  margin: 0;
  font-size: 1rem;
}

.method-details a {
  color: var(--primary-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.method-details a:hover {
  color: var(--primary-hover);
}

.social-links {
  display: flex;
  gap: 1rem;
  margin-top: 0.5rem;
}

.social-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  font-size: 1.2rem;
  color: var(--text-primary);
  text-decoration: none;
}

.social-link:hover {
  background-color: var(--primary-color);
  color: white;
  transform: translateY(-3px);
}

.contact-form {
  background: #f8f8f8;
  padding: 2rem;
  border-radius: 16px;
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
  color: var(--text-primary);
}

input, textarea {
  width: 100%;
  padding: 0.8rem 1rem;
  border-radius: 8px;
  border: 2px solid #e0e0e0;
  background: var(--card-bg);
  color: var(--text-primary);
  font-size: 1rem;
  transition: all 0.3s ease;
}

input:focus, textarea:focus {
  outline: none;
  border-color: var(--primary-color);
  box-shadow: 0 0 10px rgba(255, 107, 53, 0.1);
}

.error-input {
  border-color: #ff3b30;
}

.error-message {
  color: #ff3b30;
  margin-bottom: 1rem;
  font-size: 0.9rem;
}

.submit-btn {
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

.submit-btn:hover {
  background: var(--primary-hover);
  transform: translateY(-2px);
}

.btn-icon {
  font-size: 1.2rem;
}

.form-success {
  background-color: #e7f7ed;
  border-left: 4px solid #34c759;
  padding: 1rem;
  border-radius: 8px;
  margin-bottom: 1rem;
}

.form-success p {
  color: #2a9d4a;
  margin: 0;
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
  
  .contact-container {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
</style>
