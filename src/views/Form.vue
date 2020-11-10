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
section {
  width: 50%;
  margin: 30px 20px 10px;
  padding: 20px 50px;
  color: #c5ecfd;
  background-color: rgba(19, 19, 49, 0.7);
  -webkit-box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
  -moz-box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
  box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.3);
}
@media screen and (max-width: 1082px) {
  section {
    padding: 20px;
  }
}
@media screen and (max-width: 900px) {
  .form {
    padding: 0 20px;
  }
  section {
    margin: 10px;
  }
}
@media screen and (max-width: 686px) {
  nav {
    margin-bottom: 20px;
  }
  .form {
    display: inline-block;
  }
  section {
    width: 90%;
    padding: 30px;
    margin: 1px auto;
  }
}
@media screen and (max-width: 396px) {
  .form {
    padding: 0;
  }
  section {
    width: 100%;
    padding: 10px;
  }
}
</style>