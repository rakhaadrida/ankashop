<template>
  <div class="product">
    <Header />
    <Breadcrumb />
    <ProductDetails />
    <RelatedProduct />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Breadcrumb from "@/components/product/Breadcrumb.vue";
import ProductDetails from "@/components/product/ProductDetails.vue";
import RelatedProduct from "@/components/product/RelatedProduct.vue";

export default {
  name: "Product",
  components: {
    Header,
    Footer,
    Breadcrumb,
    ProductDetails,
    RelatedProduct,
  },
};
</script>
