<template>
  <NavBar />
  <div class="divider"></div>
  <Logo />
  <Terminal />
  <GitHubProjects />
</template>

<script>
import NavBar from './components/NavBar.vue';
import Terminal from './components/TerminalEmulator.vue';
import Logo from './components/Logo.vue';
import GitHubProjects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Terminal,
    Logo,
    GitHubProjects,
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
