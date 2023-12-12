<template>
    <nav class="navbar">
      <a href="/">
        <img src="@/assets/bikelogo.png" alt="Bike Logo" class="logo"/>
      </a>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'NavBar'
  }
  </script>
  
  <style scoped>
  .navbar {
    background-color: black;
    text-align: center;
    padding: 10px 0;
  }
  
  .logo {
    height: 100px; /* Adjust as needed */
  }
  </style>
  