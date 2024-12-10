<script setup>
import { ref, onMounted } from 'vue'

const title = "Coworkings destacados"
const coworkings = ref([])

onMounted(async () => {
  try {
    const response = await fetch('/src/assets/coworkings.json')
    if (!response.ok) {
      throw new Error('Network response was not ok')
    }
    coworkings.value = await response.json()
  } catch (error) {
    console.error('Error fetching coworkings:', error)
  }
})
</script>

<template>
  <section class="row coworking__featured">
    <div class="section__title">
      <h2>{{ title }}</h2>
    </div>
    <div v-for="coworking in coworkings" :key="coworking.id" class="col-6 col-xl-3 mb-3">
      <a :href="`ficha.html?id=${coworking.id}`">
        <div class="card">
          <img :src="coworking.imagen" :alt="coworking.nombre">
          <div class="card-body">
            <h5 class="card-title">{{ coworking.nombre }}</h5>
            <p class="card-text">Desde {{ coworking.precio }}</p>
          </div>
        </div>
      </a>
    </div>
  </section>
</template>

<style scoped>
.coworking__details {
  margin-bottom: 4rem;
}

.coworking__image {
  width: 100%;
  height: auto;
  object-fit: cover;
  border-radius: 1rem;
  margin-bottom: 1.5rem;
}

.coworking__body {
  margin-bottom: 2rem;
}

.coworking__excerpt {
  font-size: var(--font-size-title-sm);
  font-weight: var(--font-weight-bold);
  margin-bottom: 1.5rem;
}

.coworking__price {
  font-size: var(--font-size-title-xs);
  margin-bottom: 1.5rem;
}
</style>