<template>
    <div class="hamburger"  @mouseenter="toggleActive" @mouseleave="toggleActive" @click="toggleMenue">
        <span  :class="{active: is_active, line01x: menu_active}" class="myLine line01"></span>
        <span v-if="!menu_active" class="myLine line02" :class="{active: is_active}"></span>
        <span class="myLine line03" :class="{active: is_active, line03x: menu_active}"></span>
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
/* .top_icon {
  background: #29afd1;
  display: inline-block;
  border-radius: 500px;
  margin: 10px;
  position: relative;
  padding: 30px;
} */
.hamburger {
  width: 60px;
  height: 40px;
  cursor: pointer;
  margin-top: 20px;
  margin-left: 10px;
  position: relative;
}
.myLine {
    left: 0%;
    position: absolute;
    height: 10px;
    width: 100%;
    background: white;
    border-radius: 10px;
    transition: all cubic-bezier(.32,.16,.27,2.0) 0.2s;
}
.active {
    border-radius: 15px;
    transform: scaleY(1.3);
    background: #00d9bc;
    
}
.line01 {
  top: 0%;
}
.line01x {
    top: 50%;
    transform: rotate(45deg) scaleX(1.2);
}

.line02 {
  top: 50%;
}

.line03 {
  top: 100%;
}
.line03x {
    top: 50%;
    transform: rotate(-45deg) scaleX(1.2);
}
</style>