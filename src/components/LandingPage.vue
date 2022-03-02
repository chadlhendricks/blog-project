<template>
  <section>
   <div class="row">
     <div class="col-sm-auto col-md-auto col-lg- col-xl- col-xxl" id="landingtitle">
       <h1>Hi there</h1>
     </div>

     <div class="col-sm-auto col-md-auto col-lg- col-xl- col-xxl" id="landingform">
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
export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      fetch("https://fente.herokuapp.com/users", {
        method: "POST",
        body: JSON.stringify({
          email: this.email,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          localStorage.setItem("jwt", json.jwt);
          alert("User logged in");
          this.$router.push({ name: "Products" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
};</script>

<style scoped>
section {
  width: 100%;
  height: 100vh;
  margin: auto;
  background-image: url("../assets/images/logos/de-an-sun-b57RqS-nQ1c-unsplash.jpg");
  background-size: cover;
  text-align: center;
  position: relative;
  z-index: 10;
}

h1 {
  color: red;
  font-size: 200px;
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
}
.neu-border-inset {
  border-radius: 30px;
  background: #f5f5f5;
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

#landingform {
  -webkit-animation: slide-right 1.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	        animation: slide-right 1.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}

@-webkit-keyframes slide-right {
  0% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
  100% {
    -webkit-transform: translateX(100px);
            transform: translateX(100px);
  }
}
@keyframes slide-right {
  0% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
  100% {
    -webkit-transform: translateX(100px);
            transform: translateX(100px);
  }
}


@media screen and (max-width: 500px) {
#landingtitle {
  margin-top: 0px;
  top: 0;
}
}

</style>
