<template>
  <!-- Product Shop Section Begin -->
  <section class="product-shop spad page-details">
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <div class="row">
            <div class="col-lg-6">
              <div class="product-pic-zoom">
                <img class="product-big-img" :src="picDefault" alt />
              </div>
              <div class="product-thumbs">
                <carousel
                  class="product-thumbs-track ps-slider"
                  :nav="false"
                  :dots="false"
                  :autoplay="true"
                  :items="3"
                >
                  <div
                    class="pt"
                    @click="changePic(picThumbs[0])"
                    :class="picThumbs[0] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/bag-1.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[1])"
                    :class="picThumbs[1] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/bag-2.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[2])"
                    :class="picThumbs[2] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/bag-3.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[3])"
                    :class="picThumbs[3] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/bag-4.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[4])"
                    :class="picThumbs[4] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/bag-5.jpg" alt />
                  </div>
                </carousel>
              </div>
            </div>
            <div class="col-lg-6">
              <div class="product-details text-left">
                <div class="pd-title">
                  <span>Bag</span>
                  <h3>August Sling Bag</h3>
                </div>
                <div class="pd-desc">
                  <p>Stylish dan elegant sling bag with two color available. National Flag and Garuda Symbol make this bag looks powerful. Grab this product and celebrate our Indepedence Month with more fashionable looks.</p>
                  <p>
                    <b>Material :</b>
                    <br />Cordura 1000D
                    <br />Synthetic Leather
                    <br />YKK Vislon Zipper
                    <br />
                  </p>
                  <p>
                    <b>Colors:</b> Green & Black.
                  </p>
                  <p>
                    <b>Dimensions:</b>
                    <br />Length X Width X Height
                    <br />19cm X 8cm X 30cm
                  </p>
                  <p></p>
                  <h4>$17.00</h4>
                </div>
                <div class="quantity">
                  <router-link to="/cart" class="primary-btn pd-cart">Add To Cart</router-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Product Shop Section End -->
</template>

<script>
import carousel from "vue-owl-carousel";

export default {
  name: "ProductDetails",
  components: {
    carousel,
  },
  data() {
    return {
      picDefault: "img/products/bag-1.jpg",
      picThumbs: [
        "img/products/bag-1.jpg",
        "img/products/bag-2.jpg",
        "img/products/bag-3.jpg",
        "img/products/bag-4.jpg",
        "img/products/bag-5.jpg",
      ],
    };
  },
  methods: {
    changePic(srcPic) {
      this.picDefault = srcPic;
    },
  },
};
</script>

<style scoped>
.product-thumbs .pt {
  margin-right: 16px;
}
</style>