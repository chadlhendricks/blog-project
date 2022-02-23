<template>
  <section>
    <!--Landing Page Banner-->
    <div class="banner">
      <div class="banner-text">
        <h1>Chem</h1>

        <p>Hi there</p>
      </div>
    </div>

    <div class="landingpagecontent">Explore</div>


  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.banner {
  width: 100vw;
  height: 60vh;
  margin: auto;
  background-image: url("https://picsum.photos/1920/1080");
  background-size: cover;
  text-align: center;
  position: relative;
  z-index: 10;
  -webkit-animation: kenburns-bottom-right 5s ease-out both;
	        animation: kenburns-bottom-right 5s ease-out both;
}

h1 {
  color: red;
  z-index: 11;
}

@-webkit-keyframes kenburns-bottom-right {
  0% {
    -webkit-transform: scale(1) translate(0, 0);
            transform: scale(1) translate(0, 0);
    -webkit-transform-origin: 84% 84%;
            transform-origin: 84% 84%;
  }
  100% {
    -webkit-transform: scale(1.25) translate(20px, 15px);
            transform: scale(1.25) translate(20px, 15px);
    -webkit-transform-origin: right bottom;
            transform-origin: right bottom;
  }
}
@keyframes kenburns-bottom-right {
  0% {
    -webkit-transform: scale(1) translate(0, 0);
            transform: scale(1) translate(0, 0);
    -webkit-transform-origin: 84% 84%;
            transform-origin: 84% 84%;
  }
  100% {
    -webkit-transform: scale(1.25) translate(20px, 15px);
            transform: scale(1.25) translate(20px, 15px);
    -webkit-transform-origin: right bottom;
            transform-origin: right bottom;
  }
}

</style>
