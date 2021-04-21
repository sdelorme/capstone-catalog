<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
      <!-- |
      <router-link to="/about">About</router-link> -->
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: "Asap", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-color: rgb(255, 80, 246);
}

#nav {
  padding: 30px;
  font-weight: bold;
  color: #f7f4f5;
}

#nav a {
  font-weight: bold;
  color: #f7f4f5;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
