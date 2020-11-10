<template>
  <div class="input-form">
    <form action="" class="input-fields">
      <label for="">Inserisci il tuo nome</label>
      <input type="text" v-model="user.name" />
      <label for="">Inserisci la tua email</label>
      <input type="text" v-model="user.email" />
      <label for="">Inserisci un testo</label>
      <textarea v-model="user.text" name="" id="" cols="30" rows="1"></textarea>
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
.input-fields {
  display: flex;
  flex-direction: column;
}
input,
textarea {
  width: 100%;
  margin-bottom: 20px;
  padding: 10px;
  background: transparent;
  border: 0px;
  border-bottom: 2px solid #c5ecfd;
  color: #c5ecfd;
}
label {
  display: block;
}
label.check {
  vertical-align: top;
  margin-right: 15px;
}
.check {
  display: inline-block;
  width: auto;
  margin: 10px 5px;
  box-shadow: none;
}
.find {
  display: flex;
  justify-content: space-around;
  margin: 10px 10px 20px;
}
@media screen and (max-width: 876px) {
  .find {
    flex-wrap: wrap;
  }
}
select {
  margin: 10px;
  padding: 5px;
  font-size: 15px;
  border-radius: 10px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
select:focus,
select:active {
  outline: none;
}
button {
  display: block;
  margin: 10px auto;
  padding: 0.3em 1.2em;
  font-weight: 600;
  font-size: 18px;
  color: rgba(28, 190, 131, 1);
  background-color: black;
  border: 1px solid rgba(28, 190, 131, 1);
  border-radius: 100px;
  background-size: 200% 100%;
  background-image: linear-gradient(
    to right,
    transparent 50%,
    rgba(28, 190, 131, 1) 50%
  );
  transition: background-position 0.3s cubic-bezier(0.19, 1, 0.22, 1) 0.1s,
    color 0.5s ease 0s, background-color 0.5s ease;
}
button:hover {
  color: rgba(255, 255, 255, 1);
  background-color: rgba(28, 190, 131, 1);
  background-position: -100% 100%;
}

button:focus,
button:active {
  outline: none;
  border: none;
}
input[type="checkbox"].css-checkbox,
input[type="radio"].css-radio {
  display: none;
}
input[type="checkbox"].css-checkbox + label.css-label,
input[type="radio"].css-radio + label.css-label {
  height: 17px;
  display: inline-block;
  line-height: 17px;
  font-size: 17px;
  padding-left: 27px;
  letter-spacing: 1px;
  vertical-align: middle;
  margin-bottom: 10px;
  color: #7a828b;
  cursor: pointer;
  -webkit-transition: background 300ms ease-in-out, color 300ms ease-in-out;
  -o-transition: background 300ms ease-in-out, color 300ms ease-in-out;
  transition: background 300ms ease-in-out, color 300ms ease-in-out;
}
input[type="checkbox"].css-checkbox + label.css-label {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/checkbox.png");
  background-repeat: no-repeat;
  background-position: 0 0;
}
input[type="checkbox"].css-checkbox + label.css-label :hover {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/checkbox-hover.png");
  background-repeat: no-repeat;
}
input[type="radio"].css-radio + label.css-label {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/radio.png");
  background-repeat: no-repeat;
  background-position: 0 0;
}

input[type="radio"].css-radio + label.css-label:hover {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/radio-hover.png");
  background-repeat: no-repeat;
}

input[type="checkbox"].css-checkbox:checked + label.css-label {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/checked.png");
  background-repeat: no-repeat;
  color: white;
}
input[type="radio"].css-radio:checked + label.css-label {
  background: url("http://minimalcoding.net/wp-content/uploads/2015/06/radio-check.png");
  background-repeat: no-repeat;
  color: white;
}
label.css-label {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
</style>