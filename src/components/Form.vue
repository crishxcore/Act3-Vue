<template>
  <div>
    <!-- Línea decorativa -->
    <hr class="divider-line" />

    <!-- Contenedor del formulario -->
    <div class="form-container">
      <h2>Contáctanos</h2>
      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="name">Nombre</label>
          <input type="text" id="name" v-model="formData.name" placeholder="Escribe tu nombre" required />
        </div>
        <div class="form-group">
          <label for="email">Correo Electrónico</label>
          <input type="email" id="email" v-model="formData.email" placeholder="Escribe tu correo" required />
        </div>
        <div class="form-group">
          <label for="message">Mensaje</label>
          <textarea id="message" v-model="formData.message" placeholder="Escribe tu mensaje" rows="5" required></textarea>
        </div>
        <button type="submit" class="btn-submit">Enviar</button>
        <p v-if="successMessage" class="success-message">{{ successMessage }}</p>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: "",
        email: "",
        message: "",
      },
      successMessage: null,
    };
  },
  methods: {
    handleSubmit() {
      this.successMessage = "¡Gracias por tu mensaje! Nos pondremos en contacto pronto.";
      this.formData = { name: "", email: "", message: "" };
    },
  },
};
</script>

<style scoped>
/* Línea decorativa */
.divider-line {
  width: 90%;
  max-width: 800px;
  margin: 0 auto 2rem;
  border: 0;
  height: 3px;
  background: linear-gradient(to right, #ffc805, #000);
}

/* Contenedor del formulario */
.form-container {
  width: 100%;
  max-width: 800px;
  margin: 2rem auto;
  padding: 2rem;
  background: linear-gradient(to bottom, #f9f9f9, #ececec);
  border-radius: 12px;
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
  border: 1px solid rgba(0, 0, 0, 0.1);
  margin-bottom: 7rem;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  font-size: 2rem;
  color: #333;
  font-weight: bold;
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-size: 1rem;
  font-weight: bold;
  color: #444;
}

input,
textarea {
  width: 100%;
  padding: 0.8rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  background: #fff;
  transition: all 0.3s ease-in-out;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #ffc805;
}

.btn-submit {
  width: 100%;
  padding: 1rem;
  font-size: 1.2rem;
  font-weight: bold;
  color: #fff;
  background-color: #ffc805;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.btn-submit:hover {
  background-color: black;
}

.success-message {
  margin-top: 1.5rem;
  text-align: center;
  font-size: 1.1rem;
  color: black;
}

@media screen and (max-width: 768px) {
  .form-container {
    padding: 1.5rem;
  }

  h2 {
    font-size: 1.8rem;
  }

  input,
  textarea {
    padding: 0.7rem;
    font-size: 0.95rem;
  }

  .btn-submit {
    font-size: 1rem;
    padding: 0.8rem;
  }
}
</style>
