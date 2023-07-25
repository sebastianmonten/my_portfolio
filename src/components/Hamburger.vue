<template>
    <div style="display: flex; justify-content: flex-start" >
        <span class="hamburger" @mouseenter="toggleActive" @mouseleave="toggleActive" @click="toggleMenue">
            <span class="myLine line01" :class="{active: is_active, line01x: menu_active}" ></span>
            <span class="myLine line02" :class="{active: is_active, line02x: menu_active}"></span>
        </span>
        <span v-if="!menu_active" class="label" @mouseenter="toggleActive" @mouseleave="toggleActive" @click="toggleMenue">
            <h2 :class="{active_label: is_active}">my-projecs</h2>
        </span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            is_active: false,
            menu_active: false
        }
    },
    methods: {
        toggleActive() {
            this.is_active = !this.is_active
            console.log("toggled")
        },
        toggleMenue() {
            this.menu_active = !this.menu_active
            console.log('toggled menue')
        }
    }
}
</script>

<style>
.hamburger {
  width: 60px;
  height: 60px;
  cursor: pointer;
  margin: 10px;
  position: relative;
  display: inline-block;
}
.myLine {
    
    left: 0%;
    position: absolute;
    height: 10px;
    width: 100%;
    background: white;
    border-radius: 10px;
    
    transition: cubic-bezier(.32,.16,.27,2.0) 0.2s;
}
.active {
    /* height: 15px;
    border-radius: 15px;
    transform: scaleY(1.3) scaleX(1.2); */
    background: white;
    /* transition: background 0.1s; */
    
}
.line01 {
  top: 20%;
  transform: rotate(-30deg)
}
.line01x {
    top: 41%;
    transform: rotate(45deg) scaleX(1.2);
}


.line02 {
  top: 63%;
  transform: rotate(30deg)
}
.line02x {
    top: 41%;
    transform: rotate(-45deg) scaleX(1.2);
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


.label {
  display: inline-block;
  font-family:'Courier New', Courier, monospace;
  font-size: 25px;
  text-align: left;
  color: white;
  font-weight: 8;
  transition: all cubic-bezier(.32,.16,.27,2.0) 0.1s;
  cursor: pointer;
}
.active_label {
  color: white;
  transform: scaleY(2);
}
</style>