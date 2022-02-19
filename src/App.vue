<template>
  <div class="top-icon" @click="showTopMenu = !showTopMenu">
    <div class="main-item menu" v-if="!showTopMenu">
      <span class="line line01"></span>
      <span class="line line02"></span>
      <span class="line line03"></span>
    </div>
    <div v-else>
      X
    </div>
  </div>
  <h1>Sebastian Montén</h1>
</template>

<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      showTopMenu: true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ddd;
  margin-top: 60px;
}
body {
  color: #ddd;
  background: #071b2b;
}
.top-icon {
  background: #29afd1;
  display: inline-block;
  border-radius: 500px;
  margin: 10px;
  position: relative;
  padding: 80px;
  cursor: pointer;
}

.main-item {
  width: 150px;
  height: 150px;
  position: relative;
}

.line {
  position: absolute;
  height: 15px;
  width: 100%;
  background: white;
  border-radius: 10px;
  transition: all cubic-bezier(0.25, 0.1, 0.28, 1.54) 0.32s;
}

.line01 {
  top: 19%;
}

.line02 {
  top: 49%;
}

.line03 {
  top: 79%;
}

.menu.close .line01 {
  transform: rotate(45deg);
  top: 49%;
}
</style>
