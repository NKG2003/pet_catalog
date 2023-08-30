<template>
  <div>
    <h1>Hello, {{ name }}!</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld2",
  props: {
    name: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: blue;
}
</style>
