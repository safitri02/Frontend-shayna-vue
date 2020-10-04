<template>
<div class="home">
<!-- <img alt="Vue logo" src="../assets/logo.png">
<HelloWorld msg="Welcome to Your Vue.js App"/> -->
<Header/> 
<HeroCarousel/>
<Produk/>
<Instagram/>
<Partner/>
<Footer/>


</div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue';
import HeroCarousel from '@/components/HeroCarousel.vue';
import Produk from '@/components/Produk.vue';
import Instagram from '@/components/Instagram.vue';
import Partner from '@/components/Partner.vue';
import Footer from '@/components/Footer.vue';

export default {
name: 'Home',
components: {
// HelloWorld
     Header,
     HeroCarousel,
     Produk,
     Instagram,
     Partner,
     Footer,
}
}
</script>
