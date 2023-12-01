<template>
  <NavBar />
  <div class="divider"></div>
  <Logo />
  <Terminal />
  <GitHubProjects />
  <ContactInfo />
</template>

<script>
import NavBar from './components/NavBar.vue';
import Terminal from './components/TerminalEmulator.vue';
import Logo from './components/Logo.vue';
import ContactInfo from './components/Footer.vue'
import GitHubProjects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Terminal,
    Logo,
    GitHubProjects,
    ContactInfo,
  }
}
</script>

<style>
@import './assets/styles.scss';

.divider {
  height: 2px;
  background-color: #ff79c6;
  margin: 10px auto;
  width: 80%;
}
</style>
