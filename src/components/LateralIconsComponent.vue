<template>
  <ul>
    <li>
      <a
        href="https://github.com/FelipeEvaldtCarvalho/"
        target="blank"
        @mouseover="mouseIn"
        @mouseout="mouseOut"
        ><ion-icon name="logo-github"></ion-icon
      ></a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/felipe-evaldt-carvalho-9ab1461aa/"
        target="blank"
        @mouseover="mouseIn"
        @mouseout="mouseOut"
        ><ion-icon name="logo-linkedin"></ion-icon
      ></a>
    </li>
    <li>
      <a
        href="https://wa.me/5551993871466"
        target="blank"
        @mouseover="mouseIn"
        @mouseout="mouseOut"
        ><ion-icon name="logo-whatsapp"></ion-icon
      ></a>
    </li>
    <div class="line"></div>
  </ul>
</template>

<script>
import gsap from "gsap";
export default {
  name: "LateralIconsComponent",
  methods: {
    mouseIn(el) {
      gsap.to(el.target, {
        y: -5,
        color: "#4cd7a9",
        duration: 0.5,
      });
    },
    mouseOut(el) {
      gsap.to(el.target, {
        y: 0,
        color: "#808080",
        duration: 0.5,
      });
    },
  },
};
</script>

<style scoped>
.line {
  height: 200px;
  width: 1px;
  border-right: 2px solid #808080;
}
ul {
  position: fixed;
  bottom: 0;
  left: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  list-style: none;
  height: 380px;
  width: 50px;
  justify-content: space-between;
}
li a {
  color: gray;
  font-size: 30px;
  transition: 1s;
}
li a :hover {
  color: #4cd7a9;
  font-size: 30px;
  position: relative;
}
@media screen and (max-width: 820px) and (min-width: 481px) {
  .line {
    height: 60px;
  }
  ul {
    left: 2%;
    height: auto;
    width: auto;
    gap: 1rem;
  }
}
@media screen and (max-width: 480px) {
  .line {
    display: none;
  }
  ul {
    display: none;
    position: fixed;
    bottom: 0;
    left: 4%;
    height: auto;
    width: auto;
    gap: 7px;
  }
}
</style>
