<template>
    <div id="sliderbody" class="component-container slider-page">      
        <article id="slider-article">
            <div class="slideshow-container">
                <div class="grid-container">
                    <div class="grid-item" v-for="(slide, index) in slides" :key="index">
                        <img :src="slide.oldImage" :alt="slide.oldText" class="slide-image old-image" />
                        <img :src="slide.newImage" :alt="slide.newText" class="slide-image new-image" />
                        <p class="slide-text old-text">{{ slide.oldText }}</p>
                        <p class="slide-text new-text">{{ slide.newText }}</p>
                    </div>
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
    
    },
    methods: {
    
    },
    computed: {
      
    }
  };
  </script>
  
  <style scoped>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }

  .grid-item {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .slide-image {
    width: 100%;
    height: auto;
    object-fit: cover;
    transition: opacity 0.3s ease;
  }

  .new-image {
    opacity: 0;
    position: absolute;
    top: 0;
    left: 0;
  }

  .grid-item:hover .new-image {
    opacity: 1;
  }

  .grid-item:hover .old-image {
    opacity: 0;
  }

  .slide-text {
    text-align: center;
    font-size: 16px;
    color: #333;
    margin-top: 10px;
  }

  .new-text {
    display: none;
  }

  .grid-item:hover .new-text {
    display: block;
  }

  .grid-item:hover .old-text {
    display: none;
  }


  
  /* Responsive adjustments */
  @media screen and (max-width: 850px) {
    .grid-container {
      grid-template-columns: 1fr; 
    }
  }
</style>






