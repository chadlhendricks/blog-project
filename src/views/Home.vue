<template>
  <div class="home">
    <Topbar/>
    <Navbar/>
    <LandingPage/>
  </div>
</template>

<script>
import Topbar from "../components/Topbar.vue";
import Navbar from "../components/Navbar.vue";
import LandingPage from "../components/LandingPage.vue";

export default {
  components: { Topbar, Navbar, LandingPage },
};
</script>
