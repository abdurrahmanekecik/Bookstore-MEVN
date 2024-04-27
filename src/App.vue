<script>
import NavBar from '@/components/NavBar.vue'
export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<template>
  <div id="app">
    <NavBar />
    <RouterView />
  </div>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Mulish:wght@300;400;600;700&display=swap');
html body {
  font-family: 'Mulish', sans-serif;
}
a {
  color: inherit;
  text-decoration: none;
}
</style>
