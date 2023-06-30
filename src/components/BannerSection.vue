<template>
  <!-- Women Banner Section Begin -->
  <section class="women-banner spad">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12 mt-5">
          <div class="product-slider">
            <Carousel v-bind="settings" :breakpoints="breakpoints">
              <Slide v-for="product in products" :key="product.id">
                <div class="product-item">
                  <div class="pi-pic">
                    <img :src="product.src" alt="" />
                    <ul>
                      <li class="w-icon active">
                        <a href="#"><i class="icon_bag_alt"></i></a>
                      </li>
                      <li class="quick-view">
                        <a :href=product.href >+ Quick View</a>
                      </li>
                    </ul>
                  </div>

                  <div class="pi-text">
                    <div class="catagory-name">{{ product.categoryName }}</div>
                    <RouterLink :to=product.href>
                      <h5>{{ product.name }}</h5>
                    </RouterLink>
                    <div class="product-price">
                      {{ product.price }}
                    </div>
                  </div>
                </div>

              </Slide>

              <template #addons>
                <Navigation />
                <Pagination />
              </template>
            </carousel>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Women Banner Section End -->
</template>

<script>

import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation, Pagination } from "vue3-carousel";

export default {
  name: "BannerSection",
  components: {
    Carousel,
    Slide,
    Navigation,
    Pagination
  },

  data: () => ({
    products: [
      { id: '1', src: 'img/products/kaktus-1.jpg', href: '/product', categoryName: 'Coat', name: 'Kaktus Plant', price: '$14.00', },
      { id: '2', src: 'img/products/kaktus-2.jpg', href: '/product', categoryName: 'Shoes', name: 'kaktus Plant 2', price: '$13.00', },
      { id: '3', src: 'img/products/kaktus-3.jpg', href: '/product', categoryName: 'Towel', name: 'kaktus Plant 3', price: '$34.00', },
      { id: '4', src: 'img/products/women-4.jpg', href: '/product', categoryName: 'Towel', name: 'Converse Shoes', price: '$34.00', },
    ],
     // carousel settings
    settings: {
      itemsToShow: 1,
      snapAlign: 'center',
    },
    // breakpoints are mobile first
    // any settings not specified will fallback to the carousel settings
    breakpoints: {
      // 700px and up
      700: {
        itemsToShow: 3.5,
        snapAlign: 'center',
      },
      // 1024 and up
      1024: {
        itemsToShow: 3,
        snapAlign: 'start',
      },
    },
  })
};


</script>

<style>
.carousel__item {
  min-height: 200px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.product-item {
  margin-right: 26px;
  min-height: 200px;
  width: 100%;
}

.product-item .pi-pic img {
  min-width: 250px;
  max-height: 700px;
}
</style>