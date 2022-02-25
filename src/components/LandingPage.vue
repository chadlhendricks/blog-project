<template>
  <section>
   <div class="row">
     <div class="col-6" id="landingtitle">
       <h1>Welcome</h1>
     </div>

     <div class="col-6">
       <form @submit.prevent="login" class="form neu-border">
      <h2 class="form-heading">Login</h2>
      <input
        class="form-input neu-border-inset"
        type="email"
        v-model="email"
        placeholder="Email"
      />
      <input
        class="form-input neu-border-inset"
        type="password"
        v-model="password"
        placeholder="Password"
      />
      <button type="submit" class="form-btn neu-border">Sign in</button>
      <!-- <div class="form-social-login">
        <button class="form-btn neu-border form-social-btn">
          <i class="fab fa-google"></i>
        </button>
        <button class="form-btn neu-border form-social-btn">
          <i class="fab fa-facebook-f"></i>
        </button>
      </div> -->

      <p>
        Not a member?
        <router-link :to="{ name: 'Register' }">Create an account</router-link>
      </p>
    </form>
     </div>
   </div>
  </section>

</template>

<script>
export default {};
</script>

<style scoped>
section {
  width: 100vw;
  height: 100vh;
  margin: auto;
  background-image: url("https://picsum.photos/1920/1080");
  background-size: cover;
  text-align: center;
  position: relative;
  z-index: 10;
}

#landingtitle {
  margin-top: 200px;
}

h1 {
  color: red;
}

.row {
  text-align: center;
  padding-top: 270px;
  backdrop-filter: blur(5px);
  height: 100vh;

}

.neu-border {
  border-radius: 30px;
  background: #ffffff73;
  box-shadow: 8px 8px 15px #e4e4e4, -8px -8px 15px #ffffff;
}
.neu-border-inset {
  border-radius: 30px;
  background: #f5f5f5;
  box-shadow: inset 8px 8px 15px #e4e4e4, inset -8px -8px 15px #ffffff8f;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 40px;
  gap: 20px;
  width: 100%;
  margin-inline: auto;
  max-width: 600px;
}

.form-heading {
  text-align: center;
  text-transform: uppercase;
}

.form-input,
.form-btn {
  border: none;
  outline: none;
  padding: 20px;
}

.form-btn {
  cursor: pointer;
  transition: all 0.1s linear;
}

.form-btn:hover {
  transform: scale(1.05);
}

.form-social-login {
  display: flex;
  justify-content: space-between;
}

.form-social-btn {
  width: 45%;
  color: #333;
}

</style>
