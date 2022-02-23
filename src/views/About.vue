<template>
  <div class="about">
    <Topbar/>
    <Navbar/>
    <h1>This is an about page</h1>
  </div>

</template>

<script>
import Topbar from "../components/Topbar.vue";
import Navbar from "../components/Navbar.vue";

export default {
  components: { Topbar, Navbar },
};
</script>

<style>
</style>
