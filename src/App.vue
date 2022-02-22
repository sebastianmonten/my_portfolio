<template>
  <div>
    <Hamburger/>
    <h1 class="name">
      <span v-for="char in name1" :key="char"> {{ char }} </span>
      <br>
      <span v-for="char in name2" :key="char"> {{ char }} </span>
    </h1>
  </div>
</template>

<script>
import Hamburger from './components/Hamburger'
export default {
  name: 'App',
  components: {Hamburger},
  data() {
    return {
      name1: 'Sebastian',
      name2: 'Montén'
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
  /* margin-top: 60px; */
  background: #071b2b;
}
body {
  color: #ddd;
  background: #071b2b;
}

h1 {
    font-size: 62px;
    color: white;
    text-align: left;
}

h1 span { 
    display: inline-block;
    /* -webkit-transition: all 0.1s ease-out; */
    transition: all cubic-bezier(.32,.16,.27,2.0) 0.1s;
    
}

h1 span:hover {
    /* -webkit-transform: scale(2.0); */
    color: #00d9bc;
    transform: scaleY(1.8);
    cursor: pointer;
}
</style>
