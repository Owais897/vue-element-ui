<template>
  <div id="app">
    <div class="center examplex">
      <div class="square">
        <router-view />
      </div>
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  background: #e6e6e6;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.center .vs-navbar {
  min-height: 60px !important;
}
.center .vs-navbar__item a {
  color: #2c3e50;
  font-size: 15px;
  font-weight: 600;
  text-decoration: none;
}
.brand {
  width: auto;
  height: 40px;
}
.square {
  margin-top: 70px;
}
</style>
