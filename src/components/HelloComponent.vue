<template>
  <div class="container">
    <h2>
      <span class="hoverable">O</span>
      <span class="hoverable">l</span>
      <span class="hoverable">á</span>
      <span class="hoverable">,</span>
      <span class="hoverable"> m</span>
      <span class="hoverable">e</span>
      <span class="hoverable"> c</span>
      <span class="hoverable">h</span>
      <span class="hoverable">a</span>
      <span class="hoverable">m</span>
      <span class="hoverable">o</span>
    </h2>
    <Transition appear @appear="typeWrite">
      <h1 ref="name" class="main-title">Felipe Carvalho,</h1>
    </Transition>

    <h2>
      <span class="hoverable">s</span>
      <span class="hoverable">o</span>
      <span class="hoverable">u</span>
      <span class="hoverable"> D</span>
      <span class="hoverable">e</span>
      <span class="hoverable">s</span>
      <span class="hoverable">e</span>
      <span class="hoverable">n</span>
      <span class="hoverable">v</span>
      <span class="hoverable">o</span>
      <span class="hoverable">l</span>
      <span class="hoverable">v</span>
      <span class="hoverable">e</span>
      <span class="hoverable">d</span>
      <span class="hoverable">o</span>
      <span class="hoverable">r</span>
      <span class="hoverable"> W</span>
      <span class="hoverable">e</span>
      <span class="hoverable">b</span>
      <span class="hoverable">.</span>
    </h2>
    <ion-icon name="chevron-down-outline"></ion-icon>
  </div>
</template>

<script>
export default {
  name: "HelloComponent",
  methods: {
    typeWrite() {
      const titleText = this.$refs.name.innerHTML.split("");
      this.$refs.name.innerHTML = " ";
      setTimeout(() => {
        titleText.forEach((letra, i) => {
          setTimeout(() => {
            this.$refs.name.innerHTML += letra;
          }, 180 * i);
        });
      }, 600);
    },
  },
};
</script>

<style scoped>
h1,
h2 {
  font-family: "Montserrat", sans-serif;
}

h2 {
  font-size: 2.5rem;
  font-weight: 200;
  letter-spacing: 5px;
  color: white;
}
h1 {
  font-weight: 400;
  font-size: 5.2rem;
  letter-spacing: 10px;
  color: #4cd7a9;
}
.container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0 20%;
  padding-bottom: 190px;
}
.main-title:after {
  content: "|";
  margin-left: 5px;
  opacity: 1;
  color: #fff;
  animation: pisca 0.7s infinite;
}
ion-icon {
  font-size: 40px;
  position: absolute;
  bottom: 0;
  left: 50%;
  color: gray;
}
@keyframes pisca {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}
@media screen and (max-width: 820px) and (min-width: 481px) {
  .container {
    margin: 0 12%;
    padding: 0;
  }
  h2 {
    font-size: 2.7rem;
    letter-spacing: 5px;
  }
  h1 {
    font-size: 3.8rem;
    letter-spacing: 10px;
  }
}
@media screen and (max-width: 480px) {
  .container {
    margin: 0 6%;
    padding: 0;
  }
  h2 {
    font-size: 1.7rem;
    letter-spacing: 5px;
  }
  h1 {
    font-size: 2.8rem;
    letter-spacing: 10px;
  }
}
</style>
