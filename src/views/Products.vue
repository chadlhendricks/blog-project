<template>
  <div class="about">
    <ProductsNav />
    <FilterSidebar />
    <Footer />
  </div>
</template>

<script>
import ProductsNav from "../components/ProductsNav.vue";
import Navbar from "../components/Navbar.vue";
import FilterSidebar from "../components/FilterSidebar.vue";
import Footer from "../components/Footer.vue";


export default {
  components: { ProductsNav, Navbar, FilterSidebar, Footer },
};
</script>

<style></style>
