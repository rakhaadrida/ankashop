<template>
  <!-- Hero Section Begin -->
  <section class="hero-section">
    <carousel class="hero-items" :items="1" :nav="false">
      <div class="single-hero-items set-bg" style="background-image: url('/img/banner-1.jpg')">
        <div class="container">
          <div class="row">
            <div class="col-lg-5">
              <h1>Inpedence Sale</h1>
              <p>
                Get
                <b>17% - 45%</b> on All Items. Also Get
                <b>Extra 8%</b> Discount For Buy 3 Products. This Sale Available Until August 31th.
              </p>
              <a href="#" class="primary-btn">Shop Now</a>
            </div>
          </div>
        </div>
      </div>
      <div class="single-hero-items set-bg" style="background-image: url('/img/banner-2.jpg')">
        <div class="container">
          <div class="row">
            <div class="col-lg-5">
              <span>Women's Fashion</span>
              <h1>New Arrival</h1>
              <p>
                New Products for Women has Arrived. Glasses, Dress, Jacket, Skirt, Shoes, Bag, and Many More.
                <b>Get Them Now!</b>
              </p>
              <a href="#" class="primary-btn">Shop Now</a>
            </div>
          </div>
        </div>
      </div>
      <div class="single-hero-items set-bg" style="background-image: url('/img/banner-3.jpg')">
        <div class="container">
          <div class="row">
            <div class="col-lg-5">
              <span></span>
              <h1>Show Your Style</h1>
              <p>
                Upload Your Best Style and Tag Us on Instagram.
                <b>$10 Vouchers</b> are Ready to Give for
                3 Winners Each.
                <b>Join Now!</b>
              </p>
              <a href="#" class="primary-btn">Shop Now</a>
            </div>
          </div>
        </div>
      </div>
    </carousel>
  </section>
  <!-- Hero Section End -->
</template>

<script>
import carousel from "vue-owl-carousel";

export default {
  name: "Hero",
  components: {
    carousel,
  },
};
</script>
