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
              <div class="product-thumbs" v-if="productDetails.gallery.length > 0">
                <carousel
                  class="product-thumbs-track ps-slider"
                  :nav="false"
                  :dots="false"
                  :autoplay="true"
                  :items="3"
                >
                  <div
                    v-for="ss in productDetails.gallery"
                    :key="ss.id"
                    class="pt"
                    @click="changePic(ss.photo)"
                    :class="ss.photo == picDefault ? 'active' : '' "
                  >
                    <img :src="ss.photo" alt />
                  </div>
                </carousel>
              </div>
            </div>
            <div class="col-lg-6">
              <div class="product-details text-left">
                <div class="pd-title">
                  <span>{{ productDetails.type }}</span>
                  <h3>{{ productDetails.name }}</h3>
                </div>
                <div class="pd-desc">
                  <p v-html="productDetails.description"></p>
                  <h4>${{ productDetails.price }}</h4>
                </div>
                <div class="quantity">
                  <router-link to="/cart">
                    <a @click="saveKeranjang(productDetails.id, productDetails.name, productDetails.price, productDetails.gallery[0].photo)" href="#" class="primary-btn pd-cart">Add To Cart</a>
                  </router-link>
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
import axios from "axios";

export default {
  name: "ProductDetails",
  components: {
    carousel,
  },
  data() {
    return {
      picDefault: "",
      productDetails: [],
      keranjangUser: []
    };
  },
  methods: {
    changePic(srcPic) {
      this.picDefault = srcPic;
    },
    setDataPicture(data) {
      this.productDetails = data;
      this.picDefault = data.gallery[0].photo;
    },
    saveKeranjang(idProduct, nameProduct, priceProduct, photoProduct) {
      var productStored = {
        "id": idProduct,
        "name": nameProduct,
        "price": priceProduct,
        "photo": photoProduct
      }

      this.keranjangUser.push(productStored);
      const parsed = JSON.stringify(this.keranjangUser);
      localStorage.setItem('keranjangUser', parsed);
    }
  },
  mounted() {
    if (localStorage.getItem('keranjangUser')) {
      try {
        this.keranjangUser = JSON.parse(localStorage.getItem('keranjangUser'));
      } catch(e) {
        localStorage.removeItem('keranjangUser');
      }
    }
    axios
      .get("http://ankashop.test/api/product", {
        params: {
          id: this.$route.params.id
        }
      })
      .then((res) => (this.setDataPicture(res.data.data)))

      .catch((err) => console.log(err));
  },
};
</script>

<style scoped>
.product-thumbs .pt {
  margin-right: 16px;
}
</style>