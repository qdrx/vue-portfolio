<template>
    <nav class="navbar">
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'AppNavbar'
  };
  </script>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: black;
    padding: 20px;
  }
  
  .navbar ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  
  .navbar ul li {
    display: inline;
    margin: 5vw;
  }
  
  .navbar ul li a {
    text-decoration: none;
    color: #f8f8f2;
    transition: color 0.3s ease;
  }
  
  .navbar ul li a:hover {
    color: #ff79c6;
  }
  </style>
  