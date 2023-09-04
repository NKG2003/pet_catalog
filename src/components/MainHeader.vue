<template>
  <div class="plusPet">
    <form class="d-flex flex-wrap mx-6">
      <div class="col-md-3">
        <label for="form_pet" class="form-label">Pet name</label>
        <input class="form-control" type="text" v-model="formData.pets_name" />
      </div>
      <div class="col-md-3">
        <label for="form_content" class="form-label">Content</label>
        <input class="form-control" type="text" v-model="formData.content" />
      </div>
      <div>
        <input type="file" id="form_photo" />
      </div>
      <br />
      <a
        href="#"
        class="btn btn-primary mx-md-1 my-md-1"
        v-on:click="submitForm"
      >
        Save
      </a>
    </form>
    <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="getInfo">
      GET INFO
    </a>
    <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="deleteInfo">
      delete
    </a>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MainHeader",
  data() {
    return {
      formData: {
        pets_name: "",
        content: "",
        photo: null,
      },
      pets: [],
    };
  },
  methods: {
    async submitForm() {
      const form_photo = document.getElementById("form_photo");
      let photo = form_photo.files[0];

      const formData = new FormData();
      formData.append("pets_name", this.formData.pets_name);
      formData.append("content", this.formData.content);
      formData.append("photo", photo);

      await axios
        .post("http://172.16.4.228:8080/pets/", formData, {
          headers: {
            "Content-Type": "multipart/form-data",
          },
        })
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.error("Произошла ошибка при загрузке изображения:", error);
        });
    },
    async getInfo() {
      // let self = this;
      await axios.get("http://172.16.4.228:8080/pets/").then((response) => {
        console.log(response);
      });
    },
    test() {
      console.log(this.formData);
    },
    async deleteInfo() {
      await axios.delete("http://172.16.4.228:8080/pets/1").then((response) => {
        console.log(response);
      });
    },
  },
};
</script>

<style scoped>
* {
  font: 1.2em "Fira Sans", sans-serif;
  font-size: 20px;
}
</style>
