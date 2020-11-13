<template>
  <div class="newPost">
    <form action="">
      <h3>Inserisci i dati</h3>
      <h4>Titolo</h4>
      <input v-model="post.title" type="text" />
      <h4>Testo</h4>
      <textarea
        v-model="post.text"
        name=""
        id=""
        cols="30"
        rows="10"
      ></textarea>
      <p v-if="success" class="success-message">
        ✅ Nuovo Post aggiunto con successo
      </p>
      <button @click="save" type="submit">Salva</button>
    </form>
  </div>
</template>

<script>
import { EventBus } from "../main";

export default {
  name: "newPost",
  data() {
    return {
      success: false,
      post: {
        title: "",
        text: "",
      },
    };
  },
  methods: {
    save() {
      EventBus.$emit("addPost", this.post);
      this.success = true;
      setTimeout(() => (this.success = false), 3000);
    },
  },
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
.success-message {
  margin-top: 20px;
  padding: 20px;
  background-color: darkgrey;
}
</style>