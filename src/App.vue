<template>
  <div id="app">
    <!--<div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>-->
    <div class="container">
      <Navbar></Navbar>
      <AddNote></AddNote>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import AddNote from '@/components/AddNote.vue'

export default {
  name: 'app',
  components: {
    Navbar,
    AddNote,
  }
}
</script>

<style lang="scss">
body{
  background-color: #ddd;
}
</style>
