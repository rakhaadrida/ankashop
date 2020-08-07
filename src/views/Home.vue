<template>
  <div class="home">
    <Header />
    <Hero />
    <WomenBanner />
    <InstaGallery />
    <Partner />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Hero from "@/components/home/Hero.vue";
import WomenBanner from "@/components/home/WomenBanner.vue";
import InstaGallery from "@/components/home/InstaGallery.vue";
import Partner from "@/components/home/Partner.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Hero,
    WomenBanner,
    InstaGallery,
    Partner,
    Footer,
  },
};
</script>
