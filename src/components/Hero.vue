<script setup>
  const title = "Encuentra tu lugar de trabajo perfecto";
</script>

<template>
  <section class="container-fluid hero">
  <div class="hero__title mb-4">
    <h1>{{ title }}</h1>
  </div>
  <div class="hero__search">
    <div class="input-group mb-3">
      <input type="search" class="form-control" placeholder="Buscar coworking" aria-label="Buscar coworking"
        aria-describedby="basic-addon2">
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button"><i class="bi bi-search"></i></button>
      </div>
    </div>
  </div>
</section>
</template>


<style scoped>
  .hero {
    background-color: var(--primary-color);
    padding: 6rem 1rem 2rem;
    margin: 0 auto;
    align-content: center;
  }

  .hero__title h1 {
    font-size: var(--font-size-title-lg);
    font-weight: var(--font-weight-bold);
    text-align: center;
    max-width: 35rem;
    margin: 0 auto;
  }

  .hero__search {
    max-width: 35rem;
    margin: 0 auto;
  }

</style>