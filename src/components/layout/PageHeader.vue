<template>
  <header class="header">
    <h2 class="text-center mt-2">
      Todo App
      <span class="rotate"
        ><img
          class="rotate"
          src="https://img.icons8.com/color/48/000000/vue-js.png"
      /></span>
      VueJS
    </h2>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
  </header>
</template>

<script>
export default {
  name: "PageHeader",
};
</script>

<style scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}

nav {
  padding: 5px;
}

.rotate {
  animation: rotation 5s infinite linear;
}

@keyframes rotation {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(359deg);
  }
}
</style>
