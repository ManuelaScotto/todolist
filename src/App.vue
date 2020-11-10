<template>
  <div id="app">
    <nav id="nav">
      <router-link to="/">Home</router-link><span>|</span>
      <router-link to="/form">Form</router-link><span>|</span>
      <router-link to="/listPost">List Post</router-link>
    </nav>
    <router-view />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  outline: none;
}
#app {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
a {
  text-decoration: none;
  font-size: 1.5rem;
  font-weight: 600;
  color: darkblue;
}
a:active,
a:focus {
  color: darkcyan;
}
nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 20px;
  background-color: white;
  -webkit-box-shadow: 0px 0px 41px -22px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 0px 0px 41px -22px rgba(0, 0, 0, 0.75);
  box-shadow: 0px 0px 41px -22px rgba(0, 0, 0, 0.75);
}
nav span {
  font-size: 1.8rem;
  margin: 0 10px;
  font-weight: 500;
}
</style>
