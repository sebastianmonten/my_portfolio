<template>
    <div 
        class="image-container"
        @mouseover="showOverlay = true"
        @mouseout="showOverlay = false"
    >
        <div class="square-container">
            <img :src="getImageSrc(imageFileName)"  alt="Failed image" class="cropped-image" />
            <div v-show="showOverlay" class="overlay">
               <h2 class="project-title">{{projectName}}</h2> 
            </div>
            
        </div>
        <!-- <img src="@/assets/scroll_me.png"  alt="Failed image" style="width: 200px; height: auto;" class="custom-image" /> -->
    </div>
</template>

<script>
export default {
    props: {
        imageFileName: String,
        projectName: String,
    },
    data() {
        return {
            showOverlay: false
        }
    },
    methods: {
        getImageSrc(filename) {
            return require(`@/assets/${filename}`);
            // I had to use require function here instead of just `@/assets/${filename}`, so that the `@` alias will work
        }
    }
}
</script>

<style>
.image-container {
  padding: 10px;
  position: relative;
  display: inline-block;
  top: 50%;
}

.square-container {
  position: relative;
  width: 300px; /* Adjust this value to your desired square size */
  height: 300px; /* Same as width to make it square */
  overflow: hidden;
  transition: all cubic-bezier(.32,.16,.27,2.0) 0.1s;
}

.square-container:hover {
    transform: scale(1.05);
}

.cropped-image {
  position: absolute;
  top: 50%; /* Position the top edge of the image at the center of the container */
  left: 0;
  transform: translateY(-50%); /* Center the image vertically using transform */
  width: 100%; /* Make the image cover the entire container width */
  height: auto; /* Maintain the original image aspect ratio */
}

.overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 30%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black background */
  display: flex;
  align-items: center;
  justify-content: center;
}

.project-title {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 25px;
  color: white;
  /* background-color: rgba(0, 0, 0, 0.5); */
  padding: 0px;
  margin: 0;
  text-align: center;

  /* max-width: 80%;  */
  /* Adjust the width as needed */
}
</style>