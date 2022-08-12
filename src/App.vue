<template>
  <div id="app">
    <Header />
    <router-view />
    <PageFooter class="footer" />
  </div>
</template>

<script>
import Header from "./components/layout/PageHeader";
import PageFooter from "./components/layout/PageFooter.vue";
export default {
  components: {
    Header,
    PageFooter,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
}

nav a:hover {
  color: #42b983 !important;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.footer {
  min-width: 100vw;
  position: fixed;
  bottom: 0;
  text-align: center;
  font-size: 14px;
}
</style>
