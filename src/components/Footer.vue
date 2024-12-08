<script setup>
  const title = "Soy el componente footer";
</script>

<template>
  <div>
    <h2>{{ title }}</h2>
  </div>
</template>


<style scoped>
  footer {
  background-color: #000;
  color: #fff;
  padding: 20px 0;
  position: static;
  bottom: 0;
  width: 100%;
  text-align: center;
}

footer p {
  font-size: var(--font-size-small);
}
</style>