<template>
  <div class="about">
    <!-- <Topbar /> -->
    <Navbar />
    <FilterSidebar />
    <Footer />
  </div>
</template>

<script>
import Topbar from "../components/Topbar.vue";
import Navbar from "../components/Navbar.vue";
import FilterSidebar from "../components/FilterSidebar.vue";
import Footer from "../components/Footer.vue";


export default {
  components: { Topbar, Navbar, FilterSidebar, Footer },
};
</script>

<style></style>
