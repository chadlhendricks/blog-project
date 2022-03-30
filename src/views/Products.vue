<template>
  <Navbar2 />
  <ProductPage />
  <Footer />
</template>

<script>
import ProductPage from "../components/ProductPage.vue";
import Navbar2 from "../components/Navbar2.vue";
import Footer from "../components/Footer.vue";

export default {
  components: { ProductPage, Navbar2, Footer },
};
</script>

<style></style>
