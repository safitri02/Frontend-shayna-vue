<template>

<!-- Women Banner Section Begin -->
<section class="women-banner spad">
<div class="container-fluid">
<div class="row">
<div class="col-lg-12 mt-5" v-if="products.length > 0">
<carousel class="product-slider" :items="3" :autoplay="true" :nav="false">
<div class="product-item" v-for="itemProduct in products" v-bind:key="itemProduct.id">
     <div class="pi-pic">
          <img v-bind:src="itemProduct.galeri[0].photo" alt="" />
          <ul>
               <li class="w-icon active">
               <a href="#"><i class="icon_bag_alt"></i></a>
               </li>
               <li class="quick-view"><router-link to="/product">+ Quick View</router-link></li>
          </ul>
     </div>
     <div class="pi-text">
          <div class="catagory-name">{{ itemProduct.type }}</div>
          <router-link to="/product">
               <h5>{{ itemProduct.name}}</h5>
          </router-link>
          <div class="product-price">
               $ {{ itemProduct.price }}
               <span>$35.00</span>
          </div>
     </div>
</div>
<div class="product-item">
     <div class="pi-pic">
          <img src="img/products/women-2.jpg" alt="" />
          <ul>
               <li class="w-icon active">
               <a href=""><i class="icon_bag_alt"></i></a>
               </li>
               <li class="quick-view"><a href="#">+ Quick View</a></li>
          </ul>
     </div>
     <div class="pi-text">
          <div class="catagory-name">Shoes</div>
          <a href="#">
               <h5>Guangzhou sweater</h5>
          </a>
          <div class="product-price">
               $13.00
          </div>
     </div>
</div>
<div class="product-item">
     <div class="pi-pic">
          <img src="img/products/women-3.jpg" alt="" />
          <ul>
               <li class="w-icon active">
               <a href="#"><i class="icon_bag_alt"></i></a>
               </li>
               <li class="quick-view"><a href="#">+ Quick View</a></li>
          </ul>
     </div>
     <div class="pi-text">
          <div class="catagory-name">Towel</div>
          <a href="#">
               <h5>Pure Pineapple</h5>
          </a>
          <div class="product-price">
               $34.00
          </div>
     </div>
</div>
<div class="product-item">
     <div class="pi-pic">
          <img src="img/products/women-4.jpg" alt="" />
          <ul>
               <li class="w-icon active">
               <a href="#"><i class="icon_bag_alt"></i></a>
               </li>
               <li class="quick-view"><a href="#">+ Quick View</a></li>
               <li class="w-icon">
               <a href="#"><i class="fa fa-random"></i></a>
               </li>
          </ul>
     </div>
     <div class="pi-text">
          <div class="catagory-name">Towel</div>
          <a href="#">
               <h5>Converse Shoes</h5>
          </a>
          <div class="product-price">
               $34.00
          </div>
     </div>
</div>
</carousel>
</div>
     <div class="col-lg-12" v-else> 
          <p> Produk terbaru belum tersedia untuk saat ini</p>
     </div>
</div>
</div>
</section>
<!-- Women Banner Section End -->

</template>
<script>
import carousel from 'vue-owl-carousel';
import axios from "axios";

export default {
     name: "Produk",
     components: {
          carousel
     },
     data() {
          return{
               products: []
          };
     },
     mounted(){
          axios
          .get("http://127.0.0.1:8000/api/products")
          .them(res => (this.products = res.data.data))
          .catsh(err => console.log(err));
     }
};
</script>

<style scoped>
.produk {
     margin-right: 25px;
}
</style>










