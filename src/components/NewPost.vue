<template>
  <div class="newPost">
    <form action="">
      <h3>Inserisci i dati</h3>
      <h4>Titolo</h4>
      <input v-model="newPost.title" type="text" />
      <h4>Testo</h4>
      <textarea
        v-model="newPost.text"
        name=""
        id=""
        cols="30"
        rows="10"
      ></textarea>
      <button @click.prevent="save" type="submit">Salva</button>
    </form>
  </div>
</template>

<script>
// import { EventBus } from "../main.js";
// import axios from "axios";
import db from "../../db.json";

export default {
  name: "newPost",
  data() {
    return {
      newPost: {
        title: "",
        text: ""
      }
    };
  },
  methods: {
    save() {
      console.log(db.posts.length);
      console.log(db.posts);
      // EventBus.$emit("eventTitle", this.newPost.title);
      // EventBus.$emit("eventText", this.newPost.text);
      db.posts.push({
        id: db.posts.length + 1,
        title: this.newPost.title,
        text: this.newPost.text
      });
      // const res = axios.post(`http://localhost:3000/posts`, this.newPosts);

      // this.posts = res.data;
      this.newPost.title = "";
      this.newPost.text = "";
    }
  }
};
</script>

<style>
h4 {
  padding: 20px;
}
.newPost input,
.newPost textarea {
  color: black;
  width: 80%;
  font-size: 16px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  border: 2px solid rgba(169, 169, 169, 0.5);
  padding: 15px;
  border-radius: 5px;
}
.newPost button {
  margin-top: 30px;
}
</style>