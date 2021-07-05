<template>
  <div>
    <form @submit.prevent="CreatePost">
      <!-- <div>
        <lable for="id">id</lable>
        <input type="text" id="id" v-model="formData.id" />
      </div> -->
      <div>
        <lable for="id">blood_group</lable>
        <input type="text" id="blood_group" v-model="formData.blood_group" />
      </div>
      <div>
        <lable for="id">stock</lable>
        <input type="text" id="stock" v-model="formData.stock" />
      </div>
      <div>
        <lable for="id">price</lable>
        <input type="text" id="price" v-model="formData.price" />
      </div>

      <button>Create Post</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "CreatePost",
  data() {
    return {
      formData: {
        blood_group: "",
        stock: "",
        price: "",
      },
    };
  },
  methods: {
    CreatePost() {
      axios
        .post("http://127.0.0.1:8000/api/blood_banks", this.formData)
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped></style>
