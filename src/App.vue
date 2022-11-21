<template>
  <div>
    <Transition appear name="nav">
      <NavComponent />
    </Transition>
    <Transition appear name="hello">
      <LateralIconsComponent />
    </Transition>
    <Transition appear name="hello">
      <HelloComponent />
    </Transition>
    <AboutComponent />
    <WorkComponent />
    <ContactComponent @toast="toastAlert" />
    <FooterComponent />
    <Transition name="toast" @beforeEnter="beforeEnter" @enter="enter">
      <SuccessAlert v-if="toast" :alertType="toastType" />
    </Transition>
  </div>
</template>
<script>
import NavComponent from "./components/NavComponent.vue";
import LateralIconsComponent from "./components/LateralIconsComponent.vue";
import HelloComponent from "./components/HelloComponent.vue";
import AboutComponent from "./components/AboutComponent.vue";
import WorkComponent from "./components/WorkComponent.vue";
import ContactComponent from "./components/ContactComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
import SuccessAlert from "./components/SuccessAlert.vue";
import gsap from "gsap";

export default {
  name: "App",
  components: {
    SuccessAlert,
    NavComponent,
    LateralIconsComponent,
    HelloComponent,
    AboutComponent,
    WorkComponent,
    ContactComponent,
    FooterComponent,
  },
  data() {
    return {
      toast: false,
    };
  },
  methods: {
    toastAlert(type) {
      this.toast = true;
      this.toastType = type;
      setTimeout(() => {
        this.toastType = null;
        this.toast = false;
      }, 4000);
    },
    beforeEnter(el) {
      el.style.opacity = 0;
    },
    enter(el) {
      gsap.to(el, {
        opacity: 1,
        duration: 1,
      });
    },
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;700;800;900&display=swap");
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
.no-scroll {
  overflow: hidden;
}
body {
  background-color: #242424;
}
html {
  scroll-behavior: smooth;
}
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-thumb {
  width: 6px;
  background-color: gray;
  border-radius: 5px;
  transition: 0.6s;
}
::-webkit-scrollbar-thumb:hover {
  background: #4cd7a9;
}
.hoverable {
  transition: 0.3s;
}
.hoverable:hover {
  color: #4cd7a9;
}
.btn {
  color: #4cd7a9;
  background-color: transparent;
  border: 2px solid #4cd7a9;
  border-radius: 30px;
  padding: 5px 30px;
  transition: 0.4s;
  font-family: "Play", sans-serif;
  font-size: 20px;
  cursor: pointer;
}
.btn:hover {
  background-color: rgb(64, 64, 64, 60%);
}
.hello-enter-from {
  opacity: 0;
}
.hello-enter-active {
  transition: all 2s ease;
  transform: scale();
}
</style>
