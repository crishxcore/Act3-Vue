<template>
  <header>
    <nav class="navbar navbar-light fixed-top">
      <div class="container-fluid">
        <button class="navbar-toggler" type="button" @click="toggleMenu">
          <span class="navbar-toggler-icon"></span>
        </button>

        <a class="navbar-brand" href="/home">
          <img src="../assets/logonav.png" alt="Workable" class="logo-img" />
        </a>

        <div class="d-flex align-items-center logout">
          <span id="user-email" class="me-3">{{ userEmail }}</span>
          <a href="/login" class="logout-link" @click.prevent="logout">
            <i class="bi bi-power logout-icon"></i>
          </a>
        </div>
      </div>
    </nav>

    <div id="sideMenu" class="sidenav" :style="{ width: isMenuOpen ? '250px' : '0' }">
      <a href="javascript:void(0)" class="closebtn" @click="toggleMenu">&times;</a>
      <a href="/"><i class="bi bi-house"></i> Inicio</a>
      <a href="#"><i class="bi bi-search"></i> Buscar</a>
      <a href="#"><i class="bi bi-person"></i> Perfil</a>
      <a href="#"><i class="bi bi-calendar"></i> Mis reservas</a>
      <a href="#"><i class="bi bi-bell"></i> Notificaciones</a>
      <a href="#"><i class="bi bi-question-circle"></i> Ayuda</a>
    </div>
  </header>
</template>

<script>
export default {
  name: "NavMenu",
  data() {
    return {
      isMenuOpen: false, 
      userEmail: "", 
    };
  },
  mounted() {

    if (window.sessionStorage) {
      this.userEmail = sessionStorage.getItem("email");
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    logout() {
      if (window.sessionStorage) {
        sessionStorage.clear();
      }
      this.$router.push("/login");
    },
  },
};
</script>

<style scoped>
.navbar-toggler {
  border: none;
}

.navbar-brand img {
  width: 200px;
}

.sidenav {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #ffc805;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidenav a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 20px;
  color: #000;
  display: block;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #818181;
}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
}

/* Nav Logo */
.logo {
  width: 200px;
  height: auto;
  margin-bottom: 20px;
}

.logo-img {
  width: 40px;
  height: auto;
  margin-right: 10px;
}

.logout {
  position: relative;
}

.logout-icon {
  font-size: 1.5rem;
  color: black;
}

/* Nav User */
#user-email {
  display: none;
  font-size: var(--font-size-small);
  font-weight: var(--font-weight-bold);
  position: absolute;
  right: 2rem;
}

@media screen and (min-width: 768px) {
  #user-email {
    display: block;
  }
}
</style>
