<template>
  <div>
    <nav>
      <router-link class="routerLink" to="/plusPet">+ Pet </router-link> |
      <router-link class="routerLink" to="/">MyPet</router-link> |
      <router-link class="routerLink" to="/getPet">GET PET</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  components: {},
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
  text-align: center;
  padding: 20px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.routerLink {
  justify-content: space-between;
  font-size: 24px;
  text-decoration: none;
}
.routerLink:hover {
  text-decoration: underline;
}
</style>
