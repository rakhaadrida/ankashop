<template>
  <div class="product">
    <Header />
    <Breadcrumb />
    <ProductDetails />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Breadcrumb from "@/components/product/Breadcrumb.vue";
import ProductDetails from "@/components/product/ProductDetails.vue";

export default {
  name: "Product",
  components: {
    Header,
    Footer,
    Breadcrumb,
    ProductDetails,
  },
};
</script>
