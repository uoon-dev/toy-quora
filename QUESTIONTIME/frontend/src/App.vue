<template>
  <div id="app">
    <NavbarComponent />
    <router-view />
  </div>
</template>

<script>
import NavbarComponent from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    NavbarComponent
  }
};
</script>

<style>
html,
body {
  height: 100%;
}

.btn:focus {
  box-shadow: none !important;
}
</style>
