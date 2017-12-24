<template>
  <div id="container">
    <div id="title">Merry<br>Christmas!</div>
    <christmas-tree id="tree" />
  </div>
</template>

<script>

import ChristmasTree from './components/christmas-tree'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    'christmas-tree': ChristmasTree
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
}
body {
  background-image: url('./assets/background.jpg');
  background-size: cover;
}
#container {
  width: 100%;
  height: 100%;
  position: relative;
}
#title {
  position: absolute;
  text-align: center;
  top: 100px;
  right: 100px;
  font-size: 150px;
  font-family: 'Great Vibes', cursive;
  color: #990000;
}
#tree {
  position: absolute;
  width: 100%;
  height: 100%;
}
</style>
