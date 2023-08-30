<template>
  <div>
    <!-- <MainHeader></MainHeader> -->
    <Snippets></Snippets>
    <nav>
      <router-link to="/">Hello world</router-link> |
      <router-link to="/about">Second</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
// import MainHeader from "@/components/MainHeader.vue";
import Snippets from "@/components/Snippets.vue";
export default {
  components: {
    // MainHeader,
    Snippets,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
