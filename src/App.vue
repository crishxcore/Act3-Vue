<script setup>
import NavMenu from './components/NavMenu.vue'
import Hero from './components/Hero.vue'
import Icons from './components/Icons.vue'
import Coworkings from './components/Coworkings.vue'
import Form from './components/Form.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <NavMenu />
  <Hero />
    <div class="container">
      <Icons />
      <Coworkings />
      <Form />
    </div>
  <Footer />
</template>

<style scoped>

</style>
