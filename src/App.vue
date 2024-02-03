<template>
  <div>
    <div class="my_name">
      <h1>
        <span v-for="char in name1" :key="char"> {{ char }} </span>
        <br>
        <span v-for="char in name2" :key="char"> {{ char }} </span>
      </h1>
    </div>
    <!-- <Hamburger/> -->
    <Welcome/>
    <Project imageFileName="led_frack.png" projectName="FFT Tail Coat"/>
    <Project imageFileName="kth_logo.png" projectName="Software Engineering"/>
    <Project imageFileName="ray_tracer.png" projectName="Ray Tracing Project"/>
    <Project imageFileName="patch_sjoslaget_2023.png" projectName="Design"/>
    <Project imageFileName="flappy_bird.jpg" projectName="ChipKIT uC32"/>
  </div>
</template>

<script>
import Project from './components/Project.vue'
// import Hamburger from './components/Hamburger'
import Welcome from './components/Welcome.vue'
export default {
  name: 'App',
  components: {Welcome, Project},
  data() {
    Project
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

</style>
