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

  /* Bootstrap classes */
  .form-control {
    border-radius: 25px;
    padding: 10px 20px;
    font-family: var(--font-family);
  }

  .input-group-append button {
    border-radius: 0 40px 40px 0;
    padding: 12px 20px;
    right: 0;
    background-color: white;
    border: var(--bs-border-width) solid var(--bs-border-color);
    border-left: none;
  }

  .btn {
    border-radius: 25px;
    padding: 10px 20px;
    font-family: var(--font-family);
    font-weight: var(--font-weight-bold);
    background-color: var(--primary-color);
    color: var(--text-color);
    border: none;
    padding: .75rem 2.5rem;
  }

  .btn:hover {
    color: var(--text-color);
    background-color: var(--accent-color);
    border-color: none;
  }
</style>