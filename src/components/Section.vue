<template>
    <section class="section">
      <h2>{{ title }}</h2>
      <p>{{ content }}</p>
    </section>
  </template>
  
  <script>
  export default {
    name: 'Section',
    props: {
      title: String,
      content: String
    }
  };
  </script>
  
  <style scoped>
  .section {
    padding: 50px 20px;
  }
  
  .section h2 {
    font-size: 2em;
    margin-bottom: 20px;
    color: #50fa7b;
  }
  </style>
  