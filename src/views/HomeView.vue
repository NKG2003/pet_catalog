<template>
  <div class="home">
    <HelloWorld name="Nurbek" />
    <HelloWorld2 name="Sultan" />
  </div>
</template>

<script>
// @ is an alias to /src

import HelloWorld from "@/components/HelloWorld.vue";
import HelloWorld2 from "@/components/HelloWorld2.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
    HelloWorld2,
  },
};
</script>
