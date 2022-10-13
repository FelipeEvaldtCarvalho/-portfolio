<template>
  <nav id="navbar">
    <a href="#"
      ><ion-icon class="home-icon" name="rocket-outline"></ion-icon
    ></a>
    <ul class="nav-links">
      <li><a href="#about">Sobre</a></li>
      <li><a href="#work">Trabalhos</a></li>
      <li><a href="#contact">Contato</a></li>
      <li><button class="btn">Resumo</button></li>
    </ul>
    <a class="mobile-menu" v-on:click="modalOpen = !modalOpen"
      ><ion-icon name="menu-outline"></ion-icon
    ></a>
  </nav>
  <section class="modal" v-if="modalOpen">
    <ion-icon
      class="close-btn"
      name="close-outline"
      v-on:click="modalOpen = false"
    ></ion-icon>
    <ul class="modal-list">
      <li><a href="#about" v-on:click="modalOpen = false">Sobre</a></li>
      <li><a href="#work" v-on:click="modalOpen = false">Trabalhos</a></li>
      <li><a href="#contact" v-on:click="modalOpen = false">Contato</a></li>
      <li>
        <button class="btn" v-on:click="modalOpen = false">Resumo</button>
      </li>
    </ul>
  </section>
</template>
<script>
export default {
  name: "NavComponent",
  data() {
    return {
      modalOpen: false,
    };
  },
  methods: {
    navOnTop() {
      var prevScrollpos = window.pageYOffset;
      window.onscroll = function () {
        var currentScrollPos = window.pageYOffset;
        if (prevScrollpos > currentScrollPos) {
          document.getElementById("navbar").style.top = "0";
        } else {
          document.getElementById("navbar").style.top = "-100px";
        }
        prevScrollpos = currentScrollPos;
      };
    },
  },
  mounted() {
    this.navOnTop();
  },
};
</script>
<style scoped>
ul {
  list-style-type: none;
  display: flex;
  align-items: center;
}
li {
  margin-left: 60px;
}
li a {
  text-decoration: none;
  color: white;
  font-size: 20px;
  font-family: "Play", sans-serif;
  transition: 0.4s;
}
li a:hover {
  color: #4cd7a9;
}
ion-icon {
  color: #4cd7a9;
  font-size: 50px;
}
.home-icon:hover {
  animation: shake 0.5s;
  animation-iteration-count: infinite;
}
.mobile-menu {
  display: none;
}

@keyframes shake {
  0% {
    transform: translate(1px, 1px) rotate(0deg);
  }
  10% {
    transform: translate(-1px, -2px) rotate(-1deg);
  }
  20% {
    transform: translate(-3px, 0px) rotate(1deg);
  }
  30% {
    transform: translate(3px, 2px) rotate(0deg);
  }
  40% {
    transform: translate(1px, -1px) rotate(1deg);
  }
  50% {
    transform: translate(-1px, 2px) rotate(-1deg);
  }
  60% {
    transform: translate(-3px, 1px) rotate(0deg);
  }
  70% {
    transform: translate(3px, 1px) rotate(-1deg);
  }
  80% {
    transform: translate(-1px, -1px) rotate(1deg);
  }
  90% {
    transform: translate(1px, 2px) rotate(0deg);
  }
  100% {
    transform: translate(1px, -2px) rotate(-1deg);
  }
}
#navbar {
  transition: top 0.3s;
  z-index: 10000;
  background: rgb(36, 36, 36);
  background: linear-gradient(
    180deg,
    rgba(36, 36, 36, 1) 0%,
    rgba(36, 36, 36, 1) 48%,
    rgba(36, 36, 36, 0) 100%
  );
}
nav {
  display: flex;
  align-items: center;
  padding: 20px 40px;
  justify-content: space-between;
  position: fixed;
  width: 100%;
}

@media screen and (max-width: 730px) {
  .nav-links {
    display: none;
  }
  ion-icon {
    color: #4cd7a9;
    font-size: 40px;
  }
  .mobile-menu {
    display: initial;
    cursor: pointer;
  }
  .modal {
    position: fixed;
    height: 100%;
    width: 100%;
    z-index: 10001;
    background-color: #242424;
  }
  .modal-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    width: 100%;
    gap: 1rem;
    margin-top: 50px;
  }
  .modal-list li {
    margin: 0;
  }
  .close-btn {
    position: fixed;
    right: 10px;
    top: 10px;
  }
}
@media screen and (max-width: 730px) and (min-width: 481px) {
  li a {
    font-size: 2rem;
  }
  .btn {
    font-size: 2rem;
  }
  .modal-list {
    margin-top: 100px;
  }
}
</style>
