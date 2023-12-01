<template>
    <div class="contact">
      <div class="info">
        <div class="telegram">
          <span>
            <i class="fab fa-telegram"></i>
            Telegram:
          </span>
          <a href="https://t.me/qqdrx" target="_blank">@qqdrx</a>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ContactInfo',
    mounted() {
        const script = document.createElement('script');
        script.src = 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/js/all.min.js';
        script.async = true;
        document.head.appendChild(script);
    }
  };
  </script>
  
  <style scoped>
  .contact {
    text-align: center;
    max-width: 600px;
    margin: 0 auto;
  }
  
  h2 {
    margin-bottom: 20px;
  }
  
  .info {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .info div {
    margin-bottom: 10px;
  }
  
  .info span {
    font-weight: bold;
    margin-right: 5px;
  }
  
  a {
    text-decoration: none;
    color: #0366d6;
  }
  </style>
  