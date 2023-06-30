<template>
  <div class="product">
    <HeaderSection />

    <!-- Breadcrumb Section Begin -->
    <div class="breacrumb-section text-left">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="breadcrumb-text product-more">
              <RouterLink to="/"><i class="fa fa-home"></i> Home</RouterLink>
              <span>Detail</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Breadcrumb Section Begin -->

    <!-- Product Shop Section Begin -->
    <section class="product-shop spad page-details">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="row">
              <div class="col-lg-6">
                <div class="product-pic-zoom">
                  <img class="product-big-img" :src="img_detail" alt="" />
                </div>
                <div class="product-thumbs">
                  <div class="product-thumbs-track ps-slider">
                      <Carousel id="gallery" :items-to-show="1" :wrap-around="true" v-model="currentSlide">
                        <Slide v-for="thumb  in prodTumbs" :key="thumb.id">
                          <div class="carousel__item">
                            <img :src="thumb.src" :alt="thumb.id" />
                          </div>
                        </Slide>
                      </Carousel>

                      <Carousel
                        id="thumbnails"
                        :items-to-show="carouselItemsToShow"
                        :wrap-around="true"
                        v-model="currentSlide"
                        ref="carousel"
                      >
                        <Slide v-for="thumb in prodTumbs" :key="thumb.id" class="pt">
                          <div class="carousel__item" @click="changeImage(prodTumbs.indexOf(thumb))">
                            <img class="product-thumbs img" :src="thumb.src" :alt="thumb.id" />
                          </div>
                        </Slide>
                      </Carousel>
                  </div>
                </div>
              </div>
              <div class="col-lg-6">
                <div class="product-details text-left">
                  <div class="pd-title">
                    <span>oranges</span>
                    <h3>Pure Pineapple</h3>
                  </div>
                  <div class="pd-desc">
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Corporis, error officia. Rem aperiam laborum voluptatum
                      vel, pariatur modi hic provident eum iure natus quos non a
                      sequi, id accusantium! Autem.
                    </p>
                    <p>
                      Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                      Quam possimus quisquam animi, commodi, nihil voluptate
                      nostrum neque architecto illo officiis doloremque et
                      corrupti cupiditate voluptatibus error illum. Commodi
                      expedita animi nulla aspernatur. Id asperiores blanditiis,
                      omnis repudiandae iste inventore cum, quam sint molestiae
                      accusamus voluptates ex tempora illum sit perspiciatis.
                      Nostrum dolor tenetur amet, illo natus magni veniam quia
                      sit nihil dolores. Commodi ratione distinctio harum
                      voluptatum velit facilis voluptas animi non laudantium, id
                      dolorem atque perferendis enim ducimus? A exercitationem
                      recusandae aliquam quod. Itaque inventore obcaecati, unde
                      quam impedit praesentium veritatis quis beatae ea atque
                      perferendis voluptates velit architecto?
                    </p>
                    <h4>$495.00</h4>
                  </div>
                  <div class="quantity">
                    <RouterLink to="cart" class="primary-btn pd-cart">Add To Cart</RouterLink>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Product Shop Section End -->

    <RelatedSection />
    <FooterSection />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderSection from "@/components/HeaderSection.vue";
import RelatedSection from "@/components/RelatedSection.vue";
import FooterSection from "@/components/FooterSection.vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide } from "vue3-carousel";

export default {
  name: "ProductView",
  components: {
    HeaderSection,
    FooterSection,
    RelatedSection,
    Carousel,
    Slide
  },
  data() {
    return {
      currentSlide: 0,
      prodTumbs: [
        { id: '1', src: 'img/mickey1.jpg' },
        { id: '2', src: 'img/mickey2.jpg' },
        { id: '3', src: 'img/mickey3.jpg' },
      ],
    };
  },
  computed: {
    carouselItemsToShow() {
      return this.prodTumbs.length;
    },
  },
  methods: {
    changeImage(urlImg) {
      this.currentSlide = urlImg
    }
  }
};
</script>

<style scoped>

#gallery {
  margin-bottom: 10px;
}

#gallery .carousel__slide {
  height: 650px;
  min-width: 100%;
}

#thumbnails .carousel__slide {
  margin-right: 10px;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#thumbnails .carousel__slide--active {
  border: 1px solid #e7ab3c;
}

</style>

