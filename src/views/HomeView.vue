<template>
  <div class="home">
    <HeaderSection />
    <CarauselSection />
    <BannerSection />
    <GallerySection />
    <PartnerSection />
    <FooterSection />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderSection from "@/components/HeaderSection.vue";
import CarauselSection from "@/components/CarauselSection.vue";
import BannerSection from "@/components/BannerSection.vue";
import GallerySection from "@/components/GallerySection.vue";
import PartnerSection from "@/components/PartnerSection.vue";
import FooterSection from "@/components/FooterSection.vue";
export default {
  name: "HomeView",
  components: {
    HeaderSection,
    CarauselSection,
    BannerSection,
    GallerySection,
    PartnerSection,
    FooterSection
  },
};
</script>

