<template>
  <div class="">
    <form class="d-flex flex-wrap">
      <div class="col-md-3">
        <label for="form_title" class="form-label">title</label>
        <input
          class="form-control"
          type="text"
          id="form_title"
          v-model="formData.title"
        />
      </div>
      <div class="col-md-3">
        <label for="form_code" class="form-label">code</label>
        <input
          class="form-control"
          type="text"
          id="form_code"
          v-model="formData.code"
        />
      </div>
      <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="saveForm"
        >Save</a
      >
    </form>
    <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="getInfo"
      >GET INFO</a
    >
    <!-- <div class="list-group">
      <a
        href="#"
        class="list-group-item list-group-item-action"
        aria-current="true"
        v-for="item in snippets"
      >
        <div class="d-flex w-100 justify-content-between">
          <h5 class="mb-1">{{ item.title }}</h5>
          <small>{{ item.code }}</small>
        </div>
      </a>
    </div> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Snippets",
  data() {
    return {
      formData: {
        title: "",
        code: "",
      },
    };
  },
  methods: {
    async saveForm() {
      await axios
        .post("http://172.16.4.228:8000/snippets/", this.formData)
        .then((response) => {
          console.log(response);
        });
    },
    async getInfo() {
      await axios.get("http://172.16.4.228:8000/snippets/").then((response) => {
        console.log(response);
      });
    },
  },
};
</script>

<style>
* {
  font: 1.2em "Fira Sans", sans-serif;
  font-size: 20px;
}
</style>
