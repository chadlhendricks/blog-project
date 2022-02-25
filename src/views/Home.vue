<template>
  <div class="home">
    <Navbar />
    <LandingPage />
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import LandingPage from "../components/LandingPage.vue";
import Footer from "../components/Footer.vue";

export default {
  components: { Navbar, LandingPage, Footer },
};
</script>
