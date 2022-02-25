<template>
  <div>
    <div class="my_name">
      <h1>
        <span v-for="char in name1" :key="char"> {{ char }} </span>
        <br>
        <span v-for="char in name2" :key="char"> {{ char }} </span>
      </h1>
    </div>
    <Hamburger/>
    <!-- <div style="display: flex; justify-content: flex-start">
      <span>
      <Hamburger @mouseenter="toggle_active_projects" @mouseleave="toggle_active_projects"/>
      </span>
      <span >
        <h2 class="label" :class="{active_label: active_projects}">_projecs</h2>
      </span>
    </div> -->
  </div>
</template>

<script>
import Hamburger from './components/Hamburger.vue'
export default {
  name: 'App',
  components: {Hamburger},
  data() {
    return {
      name1: 'Sebastian',
      name2: 'Montén',
      active_projects: false
    }
  },
  methods: {
    toggle_active_projects() {
        this.active_projects = !this.active_projects
    }
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ddd;
  background: #071b2b;
}
body {
  color: #ddd;
  background: #071b2b;
}
.my_name {
  /* height: 50px; */
  padding: 10px;
}

h1 {
    font-size: 69px;
    color: white;
    text-align: left;
    margin: 0px;
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

h2 {
  display: inline-block;
  font-family:'Courier New', Courier, monospace;
  font-size: 25px;
  text-align: left;
  color: white;
  font-weight: 8;
  transition: all cubic-bezier(.32,.16,.27,2.0) 0.1s;
}
.active_label {
  color: #00d9bc;
  transform: scaleY(2);
  
}

</style>
