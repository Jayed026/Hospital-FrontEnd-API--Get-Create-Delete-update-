<template>
  <div>
    <button @click="getPosts">Load Post</button>
    <br />

    <table border="1px">
      <tr>
        <th>Id</th>
        <th>blood group</th>
        <th>stock</th>
        <th>price</th>
        <th>Action</th>
      </tr>

      <tr v-for="post in posts" :key="post.id">
        <td>{{ post.id }}</td>
        <td>{{ post.blood_group }}</td>
        <td>{{ post.stock }}</td>
        <td>{{ post.price }}</td>
        <td>
          <button v-on:click="deletePost(post.id)">delete</button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PostList",

  data() {
    return {
      posts: [],
    };
  },
  methods: {
    getPosts() {
      axios
        .get("http://127.0.0.1:8000/api/blood_banks")
        .then((response) => {
          console.log(response.data);
          this.posts = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    deletePost(id) {
      axios.delete("http://127.0.0.1:8000/api/blood_banks/" + id).then(() => {
        this.getPosts();
      });
    },
  },
};
</script>

<style scoped></style>
