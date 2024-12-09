<template>
  <section class="row categories text-center my-5">
    <div class="col" v-for="category in categories" :key="category.text">
      <a href="#">
        <div class="category__icon mb-1">
          <i :class="category.icon"></i>
        </div>
        <span class="category__text">{{ category.text }}</span>
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: "Icons",
  data() {
    return {
      categories: [
        { icon: "bi bi-eye", text: "Con vistas" },
        { icon: "bi bi-building", text: "Céntrico" },
        { icon: "bi bi-arrows-fullscreen", text: "Espacioso" },
        { icon: "bi bi-clock", text: "24 horas" },
      ],
    };
  },
};
</script>

<style scoped>
.categories {
  max-width: 40rem;
  margin: 0 auto;
}

.category__icon {
  width: 4rem;
  height: 4rem;
  font-size: var(--font-size-title-sm);
  background-color: var(--primary-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.category__text {
  font-size: var(--font-size-body);
  font-weight: var(--font-weight-bold);
}

a {
  color: var(--text-color);
  text-decoration: none;
}
</style>
