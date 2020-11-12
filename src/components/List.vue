<template>
  <div class="newPost">
    <h3>I tuoi post</h3>
    <ul>
      <li v-for="post of posts" :key="post.id">
        {{ post.title }}
      </li>
    </ul>
    <!-- <li>TITLE: {{ newPost.title }}</li> -->
  </div>
</template>

<script>
import axios from "axios";

// import { EventBus } from "../main.js";

export default {
  name: "list",
  data() {
    return {
      posts: []
    };
  },
  props: {
    newPost: {
      title: String,
      text: String
    }
  },
  async created() {
    console.log("iiii");
    try {
      const res = await axios.get(`http://localhost:3000/posts`);
      this.posts = res.data;
      // const resP = axios.post(`http://localhost:3000/posts`, this.newPosts);

      // this.posts = resP.data;
    } catch (e) {
      console.error(e);
    }
  }
};
</script>

<style>
li {
  list-style: none;
  text-align: left;
  padding: 15px;
  border: 1px solid rgba(169, 169, 169, 0.5);
}
li:hover {
  background-color: rgba(169, 169, 169, 0.3);
}
</style>