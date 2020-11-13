<template>
  <div class="home">
    <div class="jumbo">
      <div class="img"></div>
      <h1>HOME</h1>
      <button @click="post = 'newPost'">New Post</button>
      <button @click="post = 'list'">List Post</button>
    </div>
    <keep-alive>
      <component :is="post"></component>
    </keep-alive>
  </div>
</template>

<script>
import NewPost from "@/components/NewPost.vue";
import List from "@/components/List.vue";

export default {
  name: "home",
  components: {
    NewPost,
    List,
  },
  data() {
    return {
      post: "newPost",
    };
  },
};
</script>

<style >
.img {
  position: absolute;
  top: 80px;
  opacity: 0.7;
  background: url("https://cdn.pixabay.com/photo/2017/01/12/17/16/postit-1975188_1280.png")
    no-repeat center;
  height: 400px;
  width: 100%;
  z-index: -1;
}
.jumbo {
  color: black;
}
.jumbo h1 {
  padding-top: 180px;
  font-size: 47px;
  margin-bottom: 50px;
}
button {
  display: inline-block;
  margin: 10px 30px 30px;
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
.newPost {
  margin: 10px auto 30px;
  -webkit-box-shadow: 0px 0px 12px -4px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 12px -4px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 12px -4px rgba(0, 0, 0, 0.5);
  width: 600px;
  background-color: rgba(255, 255, 255, 0.7);
}
.newPost h3 {
  background-color: darkgray;
  width: 100%;
  padding: 20px;
  text-align: center;
}
@media screen and (max-width: 686px) {
  .newPost {
    width: 90%;
  }
}
@media screen and (max-width: 396px) {
  .jumbo h1 {
    padding-top: 100px;
    margin-bottom: 20px;
  }
  .jumbo p {
    padding: 10px;
  }
  button {
    margin: 30px 5px;
    font-size: 15px;
  }
}
</style>