<template>
  <div class="list">
    <h1>This is LIST POST page from jsonplaceholder</h1>
    <ul v-if="posts && posts.length" :key="posts.id">
      <li v-for="post of posts" :key="post.id">
        <h3>{{ post.title }}</h3>
        <p>{{ post.body }}</p>
      </li>
    </ul>

    <ul v-if="errors && errors.length">
      <li v-for="error of errors" :key="error.id">
        {{ error.message }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "list",
  data() {
    return {
      posts: [],
      errors: []
    };
  },
  created() {
    axios
      .get(`http://jsonplaceholder.typicode.com/posts`)
      .then(response => {
        // JSON responses are automatically parsed.
        this.posts = response.data;
      })
      .catch(e => {
        this.errors.push(e);
      });
  }
};
</script>

<style >
.list {
  width: 80%;
  padding: 20px;
  margin: 30px auto;
}
.list h1 {
  margin-top: 60px;
}
.list ul {
  margin-top: 20px;
}
@media screen and (max-width: 686px) {
  .list {
    width: 90%;
  }
  .list li {
    margin-bottom: 10px;
  }
}
@media screen and (max-width: 396px) {
  .list {
    width: 100%;
  }
}
</style>