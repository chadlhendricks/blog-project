<template>
    <div class="topnav">

      <ul><i class="bi bi-cart"></i>
        Shopping Cart
      </ul>
      <ul class="dropdown">
        <button
          class="btn btn-primary dropdown-toggle"
          type="button"
          id="dropdownMenuButton"
          data-mdb-toggle="dropdown"
          aria-expanded="false"
        >
          My Account
        </button>

        <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton">
          <li>
            <router-link @click="toggleNav" :to="{ name: 'Login' }"
              >Login</router-link
            >
          </li>
          <li>
            <router-link @click="toggleNav" :to="{ name: 'Register' }"
              >Register</router-link
            >
          </li>
        </ul>
      </ul>
    </div>


</template>

<script>
export default {};
</script>

<style scoped>

.topnav {
  width: 100%;
  margin: auto;
  position: fixed;
  text-align: right;
  z-index: 200;
  background: white;
}

ul {
  display: inline-block;
}

li {
    padding: 20px;
}

a {
    color: #4f4f4f;
}

#dropdownMenuButton {
  background: transparent;
  color: #4f4f4f;
  text-transform: none;
  font-size: 16px;
  box-shadow: none;
  padding: 0;
}

#dropdownMenuButton:focus {
  outline: none;
}

</style>
