<template>
  <div class="getPet">
    <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="getInfo">
      GET INFO
    </a>

    <a
      href="#"
      class="list-group-item list-group-item-action"
      aria-current="true"
      v-for="item in pets"
      :key="item.id"
    >
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">{{ item.pets_name }}</h5>
        <small>{{ item.components }}</small>
      </div>
    </a>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      formData: {
        pets_name: "",
        content: "",
        photo: null,
      },
      pets: [{ pets_name: "", components: "" }],
    };
  },
  methods: {
    async getInfo() {
      let self = this;
      await axios.get("http://172.16.4.228:8080/pets/").then((response) => {
        self.pets = response.data;
      });
    },
    test() {
      console.log(this.formData);
    },
  },
};
</script>

<style></style>
