<template>
  <!-- Women Banner Section Begin -->
  <section class="women-banner spad">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12 mt-5" v-if="products.length > 0">
          <carousel class="product-slider" :items="3" :dots="false" :nav="false" :autoplay="true">
            <div class="product-item" v-for="itemProduct in products" :key="itemProduct.id">
              <div class="pi-pic">
                <img :src="itemProduct.gallery[0].photo" alt />
                <ul>
                  <li @click="saveKeranjang(itemProduct.id, itemProduct.name, itemProduct.price, itemProduct.gallery[0].photo)" class="w-icon active">
                    <!-- <router-link to="/cart"> -->
                    <a href="#">
                      <i class="icon_bag_alt"></i>
                    </a>
                    <!-- </router-link> -->
                  </li>
                  <li class="quick-view">
                    <router-link v-bind:to="'/product/'+itemProduct.id">Quick View</router-link>
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">{{ itemProduct.type }}</div>
                <router-link to="/product">
                  <h5>{{ itemProduct.name }}</h5>
                </router-link>
                <div class="product-price">
                  ${{ itemProduct.price }}
                  <span>{{ itemProduct.price + 5}}</span>
                </div>
              </div>
            </div>
            <!-- <div class="product-item">
              <div class="pi-pic">
                <img src="img/products/kapal-1.jpg" alt />
                <ul>
                  <li class="w-icon active">
                    <a href="#">
                      <i class="icon_bag_alt"></i>
                    </a>
                  </li>
                  <li class="quick-view">
                    <router-link to="/kapalProduct">Quick View</router-link>
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">T-Shirts</div>
                <a href="#">
                  <h5>Admit Your Ignorance</h5>
                </a>
                <div class="product-price">$20.00</div>
              </div>
            </div>
            <div class="product-item">
              <div class="pi-pic">
                <img src="img/products/tas-1.jpg" alt />
                <ul>
                  <li class="w-icon active">
                    <a href="#">
                      <i class="icon_bag_alt"></i>
                    </a>
                  </li>
                  <li class="quick-view">
                    <a href="#">Quick View</a>
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Bag</div>
                <a href="#">
                  <h5>Bird Totebag</h5>
                </a>
                <div class="product-price">$23.00</div>
              </div>
            </div>
            <div class="product-item">
              <div class="pi-pic">
                <img src="img/products/dress-1.jpg" alt />
                <ul>
                  <li class="w-icon active">
                    <a href="#">
                      <i class="icon_bag_alt"></i>
                    </a>
                  </li>
                  <li class="quick-view">
                    <a href="#">Quick View</a>
                  </li>
                  <li class="w-icon">
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Dress</div>
                <a href="#">
                  <h5>Rusuk Putih</h5>
                </a>
                <div class="product-price">
                  $28.00
                  <span>$35.00</span>
                </div>
              </div>
            </div> -->
          </carousel>
        </div>
        <div class="col-lg-12" v-else>
          <p>Data Produk Tidak Ditemukan</p>
        </div>
      </div>
    </div>
  </section>
  <!-- Women Banner Section End -->
</template>

<script>
import carousel from "vue-owl-carousel";
import axios from "axios";

export default {
  name: "WomenBanner",
  components: {
    carousel,
  },
  data() {
    return {
      products: [],
      keranjangUser: []
    };
  },
  mounted() {
    axios
      .get("http://ankashop.test/api/product")
      .then((res) => (this.products = res.data.data.data))

      .catch((err) => console.log(err));

    if (localStorage.getItem('keranjangUser')) {
      try {
        this.keranjangUser = JSON.parse(localStorage.getItem('keranjangUser'));
      } catch(e) {
        localStorage.removeItem('keranjangUser');
      }
    }
  },
  methods: {
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

      window.location.reload();
    }
  },
};
</script>

<style scoped>
.product-item {
  margin-right: 20px;
}
</style>
