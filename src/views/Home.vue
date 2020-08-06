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
import Hero from "@/components/Hero.vue";
import WomenBanner from "@/components/WomenBanner.vue";
import InstaGallery from "@/components/InstaGallery.vue";
import Partner from "@/components/Partner.vue";
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
