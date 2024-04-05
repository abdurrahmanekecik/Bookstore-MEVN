<template>
  <nav class="navbar navbar-expand-md custom-nav">
    <div class="container">
      <RouterLink v-bind:to="{ name: 'home' }" class="navbar-brand">Vue.js App </RouterLink>
      <ul class="navbar-nav">
        <li class="nav-item">
          <RouterLink v-bind:to="{ name: 'home' }" class="nav-link">Home </RouterLink>
        </li>

        <li class="nav-item">
          <RouterLink v-bind:to="{ name: 'books' }" class="nav-link">Books</RouterLink>
        </li>

        <li class="nav-item">
          <RouterLink v-bind:to="{ name: 'contacts' }" class="nav-link">Contact US</RouterLink>
        </li>

        <li class="nav-item">
          <RouterLink v-bind:to="{ name: 'login' }" class="nav-link">Login</RouterLink>
        </li>

        <li class="nav-item">
          <RouterLink v-bind:to="{ name: 'register' }" class="nav-link">Register</RouterLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style scoped>
.custom-nav {
  background-color: #063547;
  padding: 15px 0;
}

.navbar-brand {
  padding: 0;
  margin: 0;
  color: #fff;
  font-size: 24px;
  font-weight: bold;
}

.nav-link {
  padding: 10px 25px;
  color: #fff;
  text-align: center;
}
.nav-link:hover {
  color: #44b89d;
}
.active-link {
  color: #44b89d;
}
</style>
