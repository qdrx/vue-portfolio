<template>
  <NavBar/>
  <div class="divider"></div>
  <Terminal/>
</template>

<script>
import NavBar from './components/NavBar.vue';
import Terminal from './components/TerminalEmulator.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    Terminal
  }
}
</script>

<style>
@import './assets/styles.scss'; 

.divider {
  height: 2px;
  background-color: #ff79c6;
  margin: 20px auto;
  width: 80%;
}
</style>
