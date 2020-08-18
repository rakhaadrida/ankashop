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
                  :items="3"
                >
                  <div
                    class="pt"
                    @click="changePic(picThumbs[0])"
                    :class="picThumbs[0] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/kapal-1.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[1])"
                    :class="picThumbs[1] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/kapal-2.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[2])"
                    :class="picThumbs[2] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/kapal-3.jpg" alt />
                  </div>

                  <div
                    class="pt"
                    @click="changePic(picThumbs[3])"
                    :class="picThumbs[3] == picDefault ? 'active' : '' "
                  >
                    <img src="img/products/kapal-4.jpg" alt />
                  </div>
                </carousel>
              </div>
            </div>
            <div class="col-lg-6">
              <div class="product-details text-left">
                <div class="pd-title">
                  <span>T-Shirts</span>
                  <h3>Admit Your Ignorance</h3>
                </div>
                <div class="pd-desc">
                  <p>Comfortable t-shirts with amazing artwork made by @lapantigatiga. With cotton combed material, this one will give you comfy feel when wear this in every condition. Grab this product and looks more fashionable with great artwork on behind.</p>
                  <p>
                    <b>Material :</b>
                    <br />Cotton Combed 24s
                  </p>
                  <p>
                    <b>Colors:</b> Black.
                  </p>
                  <p>
                    <b>Size:</b>
                    <br />S : 48cm X 69cm
                    <br />M : 50cm X 70cm
                    <br />L : 54cm X 74cm
                    <br />XL : 55cm X 76cm
                  </p>
                  <p></p>
                  <h4>$20.00</h4>
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
      picDefault: "img/products/kapal-1.jpg",
      picThumbs: [
        "img/products/kapal-1.jpg",
        "img/products/kapal-2.jpg",
        "img/products/kapal-3.jpg",
        "img/products/kapal-4.jpg",
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