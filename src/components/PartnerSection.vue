<template>
  <!-- Partner Logo Section Begin -->
  <div class="partner-logo">
    <div class="container">
      <carousel class="logo-carousel" :itemsToShow="0.75" :autoplay="2000" :transition="2000" >
        <slide v-for="slide in 5" :key="slide">
          <img class="logo-item" src="img/logo-carousel/logo-1.png" alt="" />
          <img class="logo-item" src="img/logo-carousel/logo-2.png" alt="" />
          <img class="logo-item" src="img/logo-carousel/logo-3.png" alt="" />
          <img class="logo-item" src="img/logo-carousel/logo-4.png" alt="" />
          <img class="logo-item" src="img/logo-carousel/logo-5.png" alt="" />
        </slide>
        <template #addons>

        </template>
        
      </carousel>
    </div>
  </div>
  <!-- Partner Logo Section End -->
</template>

<script>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide } from "vue3-carousel";
export default {
  name: "PartnerSection",
  components: {
    Carousel,
    Slide,
  }
};
</script>

<style>
.logo-item {
  width: 162px; 
  margin-right: 30px;
}
</style>