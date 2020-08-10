<template>
  <div class="cart">
    <Header />
    <BreadCart />
    <Cart />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import BreadCart from "@/components/cart/Breadcrumb.vue";
import Cart from "@/components/cart/Cart.vue";

export default {
  name: "ShoppingCart",
  components: {
    Header,
    BreadCart,
    Cart,
  },
};
</script>