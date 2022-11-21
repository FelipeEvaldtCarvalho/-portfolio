<template>
  <section id="about">
    <div class="container-about">
      <div class="text">
        <div class="row">
          <h1>{{ about.title }}</h1>
          <div class="line"></div>
        </div>
        <p>
          {{ about.description }}
        </p>
      </div>
      <div class="image">
        <div class="profile">
          <img src="imgs/profile.png" alt="Perfil" height="300" />
        </div>
        <div class="outline"></div>
      </div>
    </div>
    <div class="logos">
      <div class="rowlogos">
        <img
          src="imgs/html.png"
          alt="html"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
        <img
          src="imgs/css.png"
          alt="css"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
        <img
          src="imgs/js.png"
          alt="javascript"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
      </div>
      <div class="rowlogos">
        <img
          src="imgs/vue.png"
          alt="vuejs"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
        <img
          src="imgs/php.png"
          alt="php"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
        <img
          src="imgs/laravel.png"
          alt="laravel"
          height="80"
          @mouseover="mouseIn"
          @mouseout="mouseOut"
        />
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import gsap from "gsap";
export default {
  name: "AboutComponent",
  data() {
    return {
      about: {},
    };
  },
  methods: {
    getJson() {
      axios.get("/text/text.json").then((response) => {
        this.about = response.data.about;
      });
    },
    mouseIn(el) {
      gsap.to(el.target, {
        scale: 1.2,
        duration: 0.5,
      });
    },
    mouseOut(el) {
      gsap.to(el.target, {
        scale: 1,
        duration: 0.5,
      });
    },
  },
  created() {
    this.getJson();
  },
};
</script>

<style scoped>
.container-about {
  width: 100%;
  display: flex;
  margin: 0 25px;
}
p {
  margin: 15px;
  font-family: "Montserrat", sans-serif;
  font-size: 25px;
  color: white;
  line-height: 1.9rem;
  font-weight: 200;
}
h1 {
  font-family: "Montserrat", sans-serif;
  font-weight: 400;
  color: #4cd7a9;
  font-size: 30px;
}
section {
  padding: 190px;
  padding-bottom: 0;
}
.line {
  flex-grow: 1;
  height: 2px;
  border-top: 2px solid #4cd7a9;
  margin: 0;
}
.row {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
.logos {
  padding: 75px 0;
  width: 100%;
}
.rowlogos {
  display: flex;
  padding: 30px 0;
  width: 100%;
  align-items: center;
  justify-content: space-around;
}
.text {
  padding: 20px;
  width: 65%;
}
.image {
  position: relative;
  top: -60px;
  width: 270px;
  height: 320px;
}
.profile img {
  border-radius: 15px;
  filter: grayscale(1);
  transition: 0.2s;
}
.profile {
  height: 300px;
  width: 240px;
  position: relative;
}
.profile:after {
  position: absolute;
  content: "";
  display: block;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  border-radius: 15px;
  background: #4cd7a9;
  mix-blend-mode: multiply;
  transition: 0.2s;
}
.container {
  width: 100%;
  display: flex;
  max-height: 300px;
  margin: 0 25px;
}

.outline {
  position: relative;
  top: -280px;
  right: -20px;
  height: 300px;
  width: 250px;
  border: 3px solid #4cd7a9;
  border-radius: 15px;
  z-index: -10;
  transition: 0.4s;
}
.image:hover .profile:after {
  position: absolute;
  content: "";
  display: block;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  border-radius: 100px;
  background: #ffffff;
  mix-blend-mode: multiply;
}
.image:hover .profile img {
  filter: grayscale(0);
}
.image:hover .outline {
  top: -270px;
  right: -30px;
}
/*.rowlogos img:hover {
  transform: scale(1.1);
}*/
@media screen and (max-width: 950px) and (min-width: 731px) {
  section {
    margin: 25% 12%;
    padding: 0;
  }
  .container-about {
    max-height: initial;
    margin: 3rem 0;
  }
  .logos {
    padding: 0;
  }
}
@media screen and (max-width: 820px) and (min-width: 481px) {
  section {
    margin: 0 12%;
    padding: 0;
  }
  .container-about {
    max-height: initial;
    margin: 3rem 0;
    flex-direction: column;
  }
  .text {
    padding: 0;
    width: 100%;
    gap: 1rem;
  }
  p {
    margin: 2rem 0;
  }
  .image {
    position: relative;
    top: initial;
    margin: 3rem auto;
  }
  .logos {
    padding: 0;
  }
  .rowlogos {
    gap: 10px;
    padding: 0;
    margin-bottom: 25px;
  }
  .rowlogos img {
    height: 60px;
  }
}
@media screen and (max-width: 480px) {
  section {
    margin: 0 6%;
    padding: 0;
  }
  .container-about {
    width: 100%;
    display: flex;
    max-height: initial;
    margin: 2rem 0;
    flex-direction: column;
  }
  .text {
    padding: 0;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  h1 {
    font-size: 1.6rem;
  }
  p {
    margin: 0;
    font-size: 1.2rem;
    text-align: center;
  }
  .image {
    position: relative;
    top: initial;
    margin: 3rem auto;
  }
  .logos {
    padding: 0;
  }
  .rowlogos {
    gap: 10px;
    padding: 0;
    margin-bottom: 25px;
  }
  .rowlogos img {
    height: 40px;
  }
}
</style>
