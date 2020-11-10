<template>
  <div class="form">
    <section id="inputform">
      <input-form></input-form>
    </section>
    <test-form></test-form>
  </div>
</template> 

<script>
import InputForm from "@/components/InputForm.vue";
import TestForm from "@/components/TestForm.vue";

export default {
  name: "form",
  components: {
    InputForm,
    TestForm
  },
  data() {
    return {
      user: {
        name: "",
        email: "",
        check: [],
        genre: "",
        color: ""
      }
    };
  }
};
</script>

<style>
.form {
  display: flex;
  padding: 0 70px;
}
.input-fields {
  display: flex;
  flex-direction: column;
}
section {
  color: #c5ecfd;
  margin: 30px 20px 10px;
  padding: 20px 50px;
  background-color: rgba(19, 19, 49, 0.7);
  width: 50%;
  -webkit-box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
  -moz-box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
  box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
}
label {
  display: block;
}
input,
textarea {
  margin-bottom: 20px;
  background: transparent;
  border: 0px;
  border-bottom: 2px solid #c5ecfd;
  padding: 10px;
  color: #c5ecfd;
  width: 100%;
}
.check {
  margin: 10px 5px;
  display: inline-block;
  width: auto;
  box-shadow: none;
}
label.check {
  vertical-align: top;
  margin-right: 15px;
}
.find {
  display: flex;
  margin: 10px 10px 20px;
  justify-content: space-around;
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
  font-weight: 600;
  font-size: 18px;
  color: rgba(28, 190, 131, 1);
  background-color: black;
  border: 1px solid rgba(28, 190, 131, 1);
  border-radius: 100px;
  padding: 0.3em 1.2em;
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