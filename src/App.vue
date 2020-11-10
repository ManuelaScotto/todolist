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
body {
  background: url("https://images.unsplash.com/photo-1517229501771-68639c11e03d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80")
    no-repeat top center;
  background-size: cover;
  height: 96vh;
}
#app {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
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
nav span {
  font-size: 1.8rem;
  margin: 0 10px;
  font-weight: 500;
}
</style>
