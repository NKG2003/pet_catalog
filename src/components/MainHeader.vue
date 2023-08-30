<template>
  <div class="">
    <!-- <header class="bg-success  text-dark bg-opacity-50 d-flex justify-content-around">
      <a class="list-group-item py-3 fs-3 text" href="#">MyPet</a>
      <ul id="navigator" class="d-flex justify-content-around ">
        <li class="list-group-item  px-3 py-4"><a href="#" class="text"> ПОДАТЬ ОБЪЯВЛЕНИЕ</a></li>
        <li class="list-group-item  px-3 py-4"><a href="#" class="text">О приюте </a></li>
        <li class="list-group-item  px-3 py-4"><a href="#" class="text">Нужды приюта </a></li>
        <li class="list-group-item  px-3 py-4"><a href="#" class="text">Контакты</a></li>
        <li class="list-group-item  px-3 py-4"><a href="#" class="text">Вход/Регистрация</a></li>
      </ul>
      <hr>
    </header> -->
    <form class="d-flex flex-wrap">
      <div class="col-md-3">
        <label for="form_pet" class="form-label">Pet name</label>
        <input
          class="form-control"
          type="text"
          id="form_pet"
          v-model="formData.pet"
        />
      </div>
      <!-- <div class="col-md-3">
          <label for="form_owner" class="form-label">Owner</label>
          <input
            class="form-control"
            type="text"
            id="form_owner"
            v-model="formData.owner"
          />
        </div> -->
      <div class="col-md-3">
        <label for="form_content" class="form-label">Content</label>
        <input
          class="form-control"
          type="text"
          id="form_content"
          v-model="formData.content"
        />
      </div>
      <!-- <div>
          <input type="file" @change="uploadImage" />
          <img v-if="photo" :src="photo" alt="Uploaded Image" />
        </div> -->
      <!-- <div class="col-md-3">
          <label for="gender" class="form-label">Gender</label>
          <select
            class="form-select"
            id="gender"
            required
            v-model="formData.gender"
            v-on:change="test"
          >
            <option value="3">Male</option>
            <option value="4">Female</option>
          </select>
        </div>
        <div class="col-md-3">
          <label for="pet_type " class="form-label">Pet type</label>
          <select
            class="form-select"
            id="pet_type"
            required
            v-model="formData.pet_type"
            v-on:change="test"
          >
            <option value="1">Doge</option>
            <option value="2">Cat</option>
          </select>
        </div> -->
      <br />
      <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="saveForm"
        >Save</a
      >
    </form>
    <a href="#" class="btn btn-primary mx-md-1 my-md-1" v-on:click="getInfo"
      >GET INFO</a
    >
    <br />
    <a
      href="#"
      class="btn btn-primary mx-md-1 my-md-1"
      v-on:click="deleteInfoInfo"
      >Delete Info</a
    >
    <!-- <div class="list-group">
        <a href="#" class="list-group-item list-group-item-action" aria-current="true" v-for="item in pets">
          <div class="d-flex w-100 justify-content-between">
            <h5 class="mb-1">{{ item.pet_name}}</h5>
            <small>{{ item.id}}</small>
          </div>
        </a>
      </div>   -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MainHeader",
  data() {
    return {
      formData: {
        pet: "",
        // owner: [1],
        content: "",
        // photo: null,
        // gender: null,
        // pet_type: null,
      },
    };
  },
  methods: {
    // uploadImage(event) {
    //   const selectedFile = event.target.files[0];

    //   const formData = new FormData();
    //   formData.append("image", selectedFile);
    //   axios
    //     .post("http://172.16.4.228:8000/pets/", formData, {
    //       headers: {
    //         "Content-Type": "multipart/form-data",
    //       },
    //     })
    //     .then((response) => {
    //       this.photo = response.data.photo;
    //     })
    //     .catch((error) => {
    //       console.error("Произошла ошибка при загрузке изображения:", error);
    //     });
    // },
    async saveForm() {
      await axios
        .post("http://172.16.4.228:8000/pets/", this.formData)
        .then((response) => {
          console.log(response);
        });
    },
    async getInfo() {
      // let self = this;
      await axios.get("http://172.16.4.228:8000/pets/").then((response) => {
        console.log(response);
      });
    },
    async deleteInfoInfo() {
      await axios.delete("http://172.16.4.228:8000/pets/1").then((response) => {
        console.log(response);
      });
    },
  },
  // test() {
  //   console.log(this.formData);
  // },
};
</script>

<style scoped>
* {
  font: 1.2em "Fira Sans", sans-serif;
  font-size: 20px;
}
</style>
