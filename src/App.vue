<template>
  <header>
    <h1>{{ title }}</h1>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="Contack.vue">Contact</a></li>
      </ul>
    </nav>
  </header>
  <br>
  <div class="profile-page">
    <div class="profile-container">
      <!-- Foto Profil -->
      <img src="../src/assets/SAYA.jpeg" alt="Profil" class="profile-picture">
      <!-- Penjelasan atau teks tambahan bisa ditambahkan di sini -->
      <p class="profile-description">Selamat datang di profil Sultan Fadhil!</p>
    </div>
  </div>
  <br>
  <section class="hero">
    <div class="container">
      <div class="about">
        <h2>About Me</h2>
        <p>Halo! Nama saya SULTAN FADHIL  dan saya seorang MAHASISWA Teknik Informatika . <br>Saya memiliki kegemaran <br> dalam beberapa
           bidang misal nya HACKING,STRONG MAN DAN TRADING, 
</p>
      </div>
      <div class="my-work">
        <h2>My Work</h2>
        <p>untuk perkerjaan saya pernah bekerja sebagai pendodos,dan sekarang saya saya adalah seorang investor.</p>
      </div>
      <div class="social-media">
        <h2>Connect with Me</h2>
        <ul>
          <li><a href="[GitHub_Link]" target="_blank">GitHub:DIMOY</a></li>
          <li><a href="[LinkedIn_Link]" target="_blank">LinkedIn:SULTAN FADHIL</a></li>
          <li><a href="[Twitter_Link]" target="_blank">INSTAGRAM:SULTAN FADHIL</a></li>
        </ul>
      </div>
      
    </div>
  </section>
  <br>
  <br>
  <div class="hobby-header">
    <h1>My Hobby</h1>
  </div>
  <br>
  <div class="gallery">
    <div class="gallery-item" v-for="(image, index) in images" :key="index">
      <img :src="image.src" :alt="image.alt" class="gallery-image">
      <div class="image-description">{{ image.description }}</div>
    </div>
  </div>
  <br>
  <br>
  <footer class="footer">
    <div class="container">
      <p>© 2024 Hak Cipta Terpelihara. Dibuat dengan ❤️ oleh SULTAN FADHIL.</p>
     
    </div>
  </footer>
 
</template>

<script>

export default {
  name: 'ImageGallery',
  data() {
    return {
      images: [
        { src: require('@/assets/2.jpg'), alt: 'Deskripsi Gambar 1', description: '1.BERMAIN GAME' },
        { src: require('@/assets/3.jpg'), alt: 'Deskripsi Gambar 2', description: '2.OLAHRAGA' },
        { src: require('@/assets/4.jpg'), alt: 'Deskripsi Gambar 3', description: '3.TRADING' },
        { src: require('@/assets/5.jpg'), alt: 'Deskripsi Gambar 4', description: '4.TRAVELING' }
      ]
    };
  }
}
</script>

<style scoped>
body, html {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    background-color: black; /* Warna hitam untuk latar belakang */
  }
  #app {
  min-height: 100vh;
  min-width: 100vw;
}




.gallery {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* Create two columns */
  grid-gap: 20px; /* Spacing between images */
  justify-items: center; /* Center images horizontally */
  align-items: center; /* Center images vertically */
  padding: 20px; /* Padding around the gallery container */
  background: linear-gradient(45deg, #ff69b4, #00ffff, #ff4500); /* Dynamic gradient background */
  animation: rgbAnimation 5s infinite alternate; /* RGB animation */
}

.gallery-item {
  max-width: 300px; /* Set maximum width for each image */
  border: 2px solid white; /* White border around images */
}

.gallery-image {
  width: 100%; /* Images fill 100% width of .gallery-item */
  height: auto; /* Image height adjusts automatically */
  display: block; /* Ensure images are not inline */
  margin-bottom: 10px; /* Space between image and description */
}

.image-description {
  text-align: center; /* Center the description text */
  font-size: 0.9em; /* Font size for the description */
  color: white; /* White text color */
}

@keyframes rgbAnimation {
  0% {
    background: linear-gradient(45deg, #ff69b4, #00ffff, #ff4500);
  }
  100% {
    background: linear-gradient(45deg, #ff4500, #ff69b4, #00ffff);
  }
}

.hobby-header h1 {
  font-size: 2.5em;
  color: #2c3e50;
  text-align: center;
  background: linear-gradient(45deg, #ff69b4, #00ffff, #ff4500); /* Dynamic gradient background */
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.hobby-header h1:hover {
  transform: scale(1.05);
  cursor: pointer;
}

.profile-page {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 75vh; /* Menggunakan 75% dari tinggi viewport */
  background: linear-gradient(to right, #ff7e5f, #feb47b); /* Gradient indah dari pink ke oranye */
}


.profile-container {
  text-align: center;
}

.profile-picture {
  width: 300px; /* Meningkatkan lebar foto profil */
  height: 300px; /* Meningkatkan tinggi foto profil */
  border-radius: 50%; /* Membuat foto profil menjadi bulat */
  border: 5px solid #fff; /* Border putih yang lebih tebal untuk foto profil */
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Bayangan yang lebih dalam untuk efek 3D yang lebih kuat */
  transition: transform 0.3s ease-in-out; /* Animasi transformasi saat mouse hover */
}

.profile-picture:hover {
  transform: scale(1.1); /* Membesarkan foto profil saat mouse hover */
}

.profile-description {
  margin-top: 20px;
  font-size: 1.2em;
  color: #333;
}


.footer {
  color: white; /* White text color */
  text-align: center;
  padding: 10px 0;
  background: linear-gradient(45deg, #000000, #ff0000); /* Dynamic gradient background (black to red) */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.container {
  width: 80%;
  margin: auto;
  overflow: hidden;
}

.social-links .link {
  color: white; /* White text color */
  margin: 0 10px;
}

.hero {
  background: linear-gradient(45deg, #ff69b4, #00ffff, #ff4500); /* Dynamic gradient background */
  padding: 2rem;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}

.about,
.my-work,
.social-media {
  margin-bottom: 2rem;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin-bottom: 0.5rem;
}

a {
  color: white; /* White text color */
  text-decoration: none;
}

.image1 {
  align-self: flex-end;
}

header {
  /* Gradient background with red, black, blue, white */
  background: linear-gradient(to right, red, black, blue, white);
  color: #fff;
  padding: 1rem;
}

h1 {
  margin: 0;
  font-size: 2.5rem; /* Increased font size */
}

nav ul {
  list-style: none;
  padding: 0;
}

nav ul li {
  display: inline-block;
  margin-right: 1rem;
}

nav ul li a {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem; /* Increased font size for navigation links */
}

</style>
