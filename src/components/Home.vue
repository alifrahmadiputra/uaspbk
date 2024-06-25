<template>
    <div class="home-container">
      <div class="home-content">
        <h1 class="home-title">Halo Selamat Datang di Website Saya, Alif Rahmadi Putra</h1>
        <p class="home-description">Saya merupakan Undergraduate Student dari Universitas Islam Riau</p>
        <router-link to="/about" class="btn" @click="handleAboutClick">Tentang Saya</router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      handleAboutClick() {
        this.$router.push('/about');
      }
    }
  }
  </script>
  
  <style>
  .home-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: white;    
    background-size: cover;
    background-position: center;
  }
  
  .home-content {
    text-align: center;
  }
  
  .home-title {
    font-size: 36px;
    font-weight: bold;
    color:pink;
    margin-bottom: 10px;
  }
  
  .home-description {
    font-size: 18px;
    color: pink;
    margin-bottom: 30px;
  }
  
  .btn {
    padding: 10px 20px;
    background-color: pink;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s;
  }
  
  .btn:hover {
    background-color: white;
    color: pink;
    border: 2px solid pink;
  }
  </style>
  