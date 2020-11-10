<template>
  <section class="test">
    <h1>Ciao {{ name.toUpperCase() }}</h1>
    <h2>Ecco qui i tuoi dati:</h2>
    <h4>Il mio nome è: {{ name.charAt(0).toUpperCase() + name.slice(1) }}</h4>
    <h4>La mia email è : {{ email }}</h4>
    <br />
    <p style="white-space: pre">{{ text }}</p>
    <br />
    <ul>
      <h4>Ho conosciuto il tuo sito tramite:</h4>
      <li v-for="s in check" :key="s">{{ s }}</li>
    </ul>
    <h4>Sono {{ genre }} e il mio colore preferito è {{ color }}</h4>
  </section>
</template>

<script>
import { EventBus } from "../main.js";

export default {
  name: "test",
  props: ["name", "email", "text", ["check"], "genre", "color"],

  created() {
    EventBus.$on("eventName", v => (this.name = v));
    EventBus.$on("eventEmail", v => (this.email = v));
    EventBus.$on("eventText", v => (this.text = v));
    EventBus.$on("eventCheck", v => (this.check = v));
    EventBus.$on("eventGenre", v => (this.genre = v));
    EventBus.$on("eventColor", v => (this.color = v));
  }
};
</script>

<style>
.test h1,
h2 {
  margin: 20px;
}
.test h2 {
  padding-bottom: 20px;
  border-bottom: 2px solid #c5ecfd;
}
.test h4 {
  margin: 10px;
  padding: 5px;
}
.test p {
  height: 100px;
  padding: 15px;
  border: 2px solid rgba(197, 236, 253);
  background-color: rgba(197, 236, 253, 0.1);
}
li {
  list-style: none;
}
</style>