<template>
    <div id="sliderbody" class="component-container slider-page">
          
        <article id="slider-article">
        
        <div class="slideshow-container">
          <transition name="fade" mode="out-in">
            <div class="slide" v-if="slides[currentIndex]" :key="currentIndex">
              <img :src="currentSlide.oldImage" :alt="currentSlide.oldText" class="slide-image old-image" />
              <img :src="currentSlide.newImage" :alt="currentSlide.newText" class="slide-image new-image" />
              <p class="old-text">{{ currentSlide.oldText }}</p>
              <p class="new-text">{{ currentSlide.newText }}</p>
            </div>
          </transition>
          <div class="controls">
            <button class="control prev" @click="prev">&#10094; Previous</button>
            <button class="control next" @click="next">&#10095; Next</button>
          </div>
        </div>
      </article>
    </div>
  </template>
  
  
  
  
  <script>
  import OldCinelli from "../assets/old-cinelli.jpeg";
  import NewCinelli from "../assets/new-cinelli.jpg";

  import OldBianchi from "../assets/old-bianchi.jpeg";
  import NewBianchi from "../assets/new-bianchi.jpeg";

  import OldPeugeot from "../assets/old-peugeot.jpeg";
  import NewPeugeot from "../assets/new-peugeot.jpeg";

  import OldColnago from "../assets/old-colnago.jpeg";
  import NewColnago from "../assets/new-colnago.jpeg";
  export default {
    name: "slidersPage",
    data() {
      return {
        slides: [
          {
            oldImage: OldBianchi,
            newImage: NewBianchi,
            oldText: "A 1950's Bianchi Folgorissima",
            newText: "A 2021 Biachi Oltre XR",
          },
          {
            oldImage: OldCinelli,
            newImage: NewCinelli,
            oldText: "A 1950's Cinelli SuperCorsa",
            newText: "A 2023 Cinelli SuperCorsa Modern",
          
          },
          {
            oldImage: OldPeugeot,
            newImage: NewPeugeot,
            oldText: "A 1950's Peugeot PX-10",
            newText: "A 2023 Peugeot R02",
          },
          {
            oldImage: OldColnago,
            newImage: NewColnago,
            oldText: "A 1970's Colnago Super Pista",
            newText: "A 2023 Colnago C68",
          }
        ],
        currentIndex: 0
      };
    },
    mounted() {
    //   this.startSlide();
    },
    methods: {
    //   startSlide() {
    //     this.timer = setInterval(this.next, 8000);
    //   },
      next() {
        this.currentIndex = (this.currentIndex + 1) % this.slides.length;
      },
      prev() {
        this.currentIndex = (this.currentIndex + this.slides.length - 1) % this.slides.length;
      }
    },
    computed: {
      currentSlide() {
        return this.slides[this.currentIndex];
      }
    }
  };
  </script>
  
  <style scoped>
  .slide {
    position: relative;
    width: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .new-image, .old-image {
    width: auto; 
    height: auto;
    object-fit: cover;
    margin: 0 auto; 
    transition: opacity 0.3s ease;
  }

  .new-image {
    opacity: 0;
    position: absolute;
    top: 0;
   
  }

  .slide:hover .new-image {
    opacity: 1;
  }

  .slide:hover .old-image {
    opacity: 0;
  }

  .old-text, .new-text {
    text-align: center;
    font-size: 16px;
    color: #333;
    margin-top: 10px;
    margin-bottom: 0px;
    /* display: none; */
  }

  .new-text {
    display: none;
  }

  .slide:hover .new-text {
    display: block;
  }

  .slide:hover .old-text {
    display: none;
  }

  .slideshow-container {
    width: 100%;
    max-width: 1200px;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
  }

  .controls {
    display: flex;
    justify-content: center;
    margin-top: 5px;
  }

  .control {
    background-color: rgba(0, 123, 167, 0.5);
    color: white;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    cursor: pointer;
    width: 150px;
  }

  .control:hover {
    background-color: #0056b3;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.9s ease;
  }

  .fade-enter, .fade-leave-to {
    opacity: 0;
  }

  @media screen and (max-width: 850px) {
    .new-image, .old-image {
      width: 100%;
      left: 0;
    }
  }

  @media screen and (max-width: 450px) {
    
  }
</style>





