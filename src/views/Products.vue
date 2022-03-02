<template>
  <Navbar/>
  <ProductsNav />
  <ProductPage/>
  <Footer />
</template>

<script>
import ProductPage from "../components/ProductPage.vue";
import ProductsNav from "../components/ProductsNav.vue";
import Navbar from "../components/Navbar.vue";
import FilterSidebar from "../components/FilterSidebar.vue";
import Footer from "../components/Footer.vue";

export default {
  components: { ProductPage, ProductsNav, Navbar, FilterSidebar, Footer },
};
</script>

<style></style>
