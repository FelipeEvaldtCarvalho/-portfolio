<template>
  <Transition
    appear
    name="nav"
    @before-appear="navBeforeAppear"
    @appear="navAppear"
  >
    <nav id="navbar">
      <a href="#"
        ><ion-icon class="home-icon" name="rocket-outline"></ion-icon
      ></a>
      <ul class="nav-links">
        <li><a href="#about">Sobre</a></li>
        <li><a href="#work">Trabalhos</a></li>
        <li><a href="#contact">Contato</a></li>
      </ul>
      <a class="mobile-menu" v-on:click="openModal"
        ><ion-icon name="menu-outline"></ion-icon
      ></a>
    </nav>
  </Transition>
  <Transition name="modal">
    <div class="modal" v-if="modalOpen">
      <ion-icon
        class="close-btn"
        name="close-outline"
        v-on:click="closeModal"
      ></ion-icon>
      <ul class="modal-list">
        <li><a href="#about" v-on:click="closeModal">Sobre</a></li>
        <li><a href="#work" v-on:click="closeModal">Trabalhos</a></li>
        <li><a href="#contact" v-on:click="closeModal">Contato</a></li>
      </ul>
    </div>
  </Transition>
</template>
<script>
import gsap from "gsap";
export default {
  name: "NavComponent",
  data() {
    return {
      modalOpen: false,
    };
  },
  methods: {
    openModal() {
      this.modalOpen = true;
      document.body.classList.add("no-scroll");
    },
    closeModal() {
      this.modalOpen = false;
      document.body.classList.remove("no-scroll");
    },
    navBeforeAppear(el) {
      el.style.transform = "translateY(-60px)";
      el.style.opacity = 0;
    },
    navAppear(el) {
      gsap.to(el, {
        duration: 1.5,
        y: 0,
        opacity: 1,
      });
    },
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
.no-scroll {
  overflow: hidden;
  position: fixed;
}
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
.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}
.modal-leave-active,
.modal-enter-active {
  transition: all 1s ease;
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
  transition: top 0.8s;
  z-index: 10;
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
.hello-enter-from {
  opacity: 0;
}
.hello-enter-active {
  transition: all 2s ease;
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
    background: rgba(84, 84, 84, 0.552);
    box-shadow: 0 8px 32px 0 rgba(37, 38, 49, 0.73);
    backdrop-filter: blur(13.5px);
    -webkit-backdrop-filter: blur(13.5px);
  }
  .modal-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
    width: 100%;
    gap: 2.5rem;
  }
  .modal-list li {
    margin: 0;
  }
  .modal-list li a {
    font-size: 2rem;
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
