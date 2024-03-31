<template>
    <div class="contact-page">
      <h2>Hubungi Kami</h2>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Nama:</label>
          <input type="text" id="name" v-model="form.name" required>
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="form.email" required>
        </div>
        <div class="form-group">
          <label for="suggestion">Saran:</label>
          <textarea id="suggestion" v-model="form.suggestion" required></textarea>
        </div>
        <button type="submit">Kirim</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ContactPage',
    data() {
      return {
        form: {
          name: '',
          email: '',
          suggestion: ''
        }
      };
    },
    methods: {
      submitForm() {
        // Proses data form di sini
        console.log('Form submitted:', this.form);
        // Kirim data ke server atau tampilkan pesan konfirmasi
      }
    }
  }
  </script>
  
  <style scoped>
  .contact-page {
    max-width: 600px;
    margin: auto;
    padding: 20px;
  }
  
  .form-group {
    margin-bottom: 10px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input[type="text"],
  input[type="email"],
  textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
  }
  
  button {
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
  }
  button:hover {
    background-color: #0056b3;
  }
  </style>
  