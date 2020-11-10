<template>
  <div class="input-form">
    <form action="" class="input-fields">
      <label for="">Inserisci il tuo nome</label>
      <input type="text" v-model="user.name" />
      <label for="">Inserisci la tua email</label>
      <input type="text" v-model="user.email" />
      <label for="">Inserisci un testo</label>
      <textarea v-model="user.text" name="" id="" cols="30" rows="2"></textarea>
      <label for="">Come hai trovato il mio sito: </label>
      <div class="find">
        <input
          type="checkbox"
          id="check1"
          name="check1"
          class="check css-checkbox"
          v-model="user.check"
          value="google"
        />
        <label class="check css-label" for="check1">GOOGLE</label>
        <input
          type="checkbox"
          id="check2"
          name="check2"
          class="check css-checkbox"
          v-model="user.check"
          value="youtube"
        />
        <label class="check css-label" for="check2">YOUTUBE</label>
        <input
          type="checkbox"
          id="check3"
          name="check3"
          class="check css-checkbox"
          v-model="user.check"
          value="facebook"
        />
        <label class="check css-label" for="check3">FACEBOOK</label>
      </div>
      <label for="">Indica il tuo genere: </label>
      <div class="find">
        <input
          type="radio"
          class="check css-radio"
          v-model="user.genre"
          id="male"
          value="maschio"
        />

        <label for="male" class="check css-label">MASCHIO</label>
        <input
          type="radio"
          v-model="user.genre"
          id="female"
          value="femmina"
          class="check css-radio"
        />
        <label for="female" class="check css-label">FEMMINA</label>
      </div>
      <label for="">Indica il tuo colore preferito: </label>
      <select
        :style="{
          backgroundColor: user.color,
          color: user.color == 'black' ? 'white' : 'black'
        }"
        v-model="user.color"
        id="color"
      >
        <option value="yellow">Giallo</option>
        <option value="red">Rosso</option>
        <option value="green">Verde</option>
        <option value="orange">Arancione</option>
        <option value="blue">Blu</option>
        <option value="black">Nero</option>
        <option value="white">Bianco</option>
      </select>
      <button @click.prevent="submit" type="submit">INVIA</button>
    </form>
  </div>
</template>

<script>
import { EventBus } from "../main.js";

export default {
  name: "input-form",
  data() {
    return {
      user: {
        name: "",
        email: "",
        text: "",
        check: [],
        genre: "",
        color: ""
      }
    };
  },
  methods: {
    submit() {
      console.log(this.user.check);
      EventBus.$emit("eventName", this.user.name);
      EventBus.$emit("eventEmail", this.user.email);
      EventBus.$emit("eventCheck", this.user.check);
      EventBus.$emit("eventText", this.user.text);
      EventBus.$emit("eventGenre", this.user.genre);
      EventBus.$emit("eventColor", this.user.color);
      this.user.name = "";
      this.user.email = "";
      this.user.genre = "";
      this.user.text = "";
      this.user.color = "";
    }
  }
};
</script>

<style>
</style>