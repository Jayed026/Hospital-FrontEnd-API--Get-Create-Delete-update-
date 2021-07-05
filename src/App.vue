/* eslint-disable vue/valid-template-root */
<template>
  <div>
    <CreatePost />

    <PostList />
  </div>
</template>

<script>
//import axios from "axios";
import PostList from "./components/PostList.vue";
import CreatePost from "./components/CreatePost.vue";
export default {
  name: "App",
  components: {
    CreatePost,
    PostList,
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
