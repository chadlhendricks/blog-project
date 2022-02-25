<template>
  <div class="about">
    <!-- <Topbar /> -->
    <Navbar />
    <h1>This is an about page</h1>
    <AboutUs />
    <Footer />
  </div>
</template>

<script>
import Topbar from "../components/Topbar.vue";
import Navbar from "../components/Navbar.vue";
import AboutUs from "../components/AboutUs.vue";
import Footer from "../components/Footer.vue";


export default {
  components: { Topbar, Navbar, Footer, AboutUs },
};
</script>

<style></style>
