<template>
  <!-- Related Products Section End -->
  <div class="related-products spad">
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <div class="section-title">
            <h2>Related Products</h2>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-3 col-sm-6">
          <div class="product-item">
            <div class="pi-pic">
              <img src="img/products/kapal-1.jpg" alt />
              <ul>
                <li class="w-icon active">
                  <router-link to="/kapalProduct">
                    <i class="icon_bag_alt"></i>
                  </router-link>
                </li>
                <li class="quick-view">
                  <router-link to="/kapalProduct">Quick View</router-link>
                </li>
              </ul>
            </div>
            <div class="pi-text">
              <div class="catagory-name">T-Shirts</div>
              <router-link to="/kapalProduct">
                <h5>Admit Your Ignorance</h5>
              </router-link>
              <div class="product-price">$20.00</div>
            </div>
          </div>
        </div>
        <div class="col-lg-3 col-sm-6">
          <div class="product-item">
            <div class="pi-pic">
              <img src="img/products/tas-1.jpg" alt />
              <ul>
                <li class="w-icon active">
                  <router-link to="/">
                    <i class="icon_bag_alt"></i>
                  </router-link>
                </li>
                <li class="quick-view">
                  <router-link to="/">Quick View</router-link>
                </li>
              </ul>
            </div>
            <div class="pi-text">
              <div class="catagory-name">Bag</div>
              <router-link to="/">
                <h5>Bird Totebag</h5>
              </router-link>
              <div class="product-price">$23.00</div>
            </div>
          </div>
        </div>
        <div class="col-lg-3 col-sm-6">
          <div class="product-item">
            <div class="pi-pic">
              <img src="img/products/dress-1.jpg" alt />
              <ul>
                <li class="w-icon active">
                  <router-link to="/">
                    <i class="icon_bag_alt"></i>
                  </router-link>
                </li>
                <li class="quick-view">
                  <router-link to="/">Quick View</router-link>
                </li>
              </ul>
            </div>
            <div class="pi-text">
              <div class="catagory-name">Dress</div>
              <router-link to="/">
                <h5>Rusuk Putih</h5>
              </router-link>
              <div class="product-price">
                $28.00
                <span>$35.00</span>
              </div>
            </div>
          </div>
        </div>
        <div class="col-lg-3 col-sm-6">
          <div class="product-item">
            <div class="pi-pic">
              <img src="img/products/liburan-1.jpg" alt />
              <ul>
                <li class="w-icon active">
                  <router-link to="/">
                    <i class="icon_bag_alt"></i>
                  </router-link>
                </li>
                <li class="quick-view">
                  <router-link to="/">Quick View</router-link>
                </li>
              </ul>
            </div>
            <div class="pi-text">
              <div class="catagory-name">T-Shirts</div>
              <router-link to="/">
                <h5>Liburan Tee</h5>
              </router-link>
              <div class="product-price">$24.00</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Related Products Section End -->
</template>

<script>
export default {
  name: "RelatedProduct",
};
</script>