<template>
  <NavBar />
  <div>
    <button :class="{ active: currentMode === 'Slideshow' }" @click="setMode('Slideshow')">Slideshow</button>
    <button :class="{ active: currentMode === 'Gallery' }" @click="setMode('Gallery')">Gallery</button>

    <ImageSlider v-if="currentMode === 'Slideshow'"></ImageSlider>
    <ImageGallery v-else></ImageGallery>
  </div>
</template>


<script>
import ImageSlider from './components/ImageSlider.vue';
import ImageGallery from './components/ImageGallery.vue';
import NavBar from './components/NavBar.vue';

export default {
  name: 'App',
  components: {
    ImageSlider,
    ImageGallery,
    NavBar
  },
  data() {
    return {
      currentMode: 'Slideshow' 
    };
  },
  methods: {
    setMode(mode) {
      this.currentMode = mode;
    }
  }
};
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}

button {
  padding: 10px 20px;
  margin: 5px;
  border: 1px solid #2c3e50;
  background-color: white;
  cursor: pointer;
}

button.active {
  background-color: rgba(0, 123, 167, 0.5);  
  color: white;
}

button:hover {
  background-color: #0056b3;
  color: white;
}
</style>

