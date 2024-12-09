<template>
  <footer class="footer">
    <div class="container-fluid">
      <p>&copy; 2024 Workable. Todos los derechos reservados.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
footer {
  background-color: #000;
  color: #fff;
  padding: 20px 0;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  text-align: center;
  z-index: 1000; 
}

footer p {
  font-size: var(--font-size-small);
}
</style>
