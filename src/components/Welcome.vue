<template>
  <!-- <div class="center-container">
    <div class="centered-content">
      <h2>Projects</h2>
    </div>
  </div> -->
  
  <div class="centered-container">
    <div class="image-container">
      <img src="../assets/scroll_me.png"  alt="Your Image" style="width: 200px; height: auto;" class="custom-image" />
      <h2 class="image-title">Projects</h2>
    </div>
  </div>

</template>

<script>
export default {
    data() {
        return {
        }
    },
    methods: {
    }
}
</script>

<style>
.centered-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 50vh;
}

.centered-content {
    font-size: 30px;
    color: gray;
    text-align: left;
    margin: 0px;
    padding: 10px;
}

.image-container {
  position: relative;
  display: inline-block;
  top: 50%;
}

.custom-image {
  width: 300px; /* Adjust to your image dimensions */
  height: auto;
}

.image-title {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 35px;
  color: white;
  padding: 10px;
  margin: 0;
  text-align: center;
}

</style>