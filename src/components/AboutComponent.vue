<template>
  <section id="about">
    <div class="container">
      <div class="text">
        <div class="row">
          <h1>Sobre mim</h1>
          <div class="line"></div>
        </div>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorum,
          expedita dolores! Quia itaque quis amet placeat quam! Quaerat, aut
          porro obcaecati harum delectus odio, vel est ab, iusto rem nihil.
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
        <img src="imgs/html.png" alt="html" height="80" />
        <img src="imgs/css.png" alt="css" height="92" />
        <img src="imgs/js.png" alt="javascript" height="90" />
        <img src="imgs/vue.png" alt="vuejs" height="80" />
      </div>
      <div class="rowlogos">
        <img src="imgs/python.png" alt="python" height="80" />
        <img src="imgs/dj.png" alt="django" height="80" />
        <img src="imgs/php.png" alt="php" height="80" />
        <img src="imgs/laravel.png" alt="laravel" height="80" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AboutComponent",
};
</script>

<style scoped>
p {
  margin: 15px;
  font-family: "Play", sans-serif;
  font-size: 25px;
  color: white;
}
h1 {
  font-family: "Montserrat", sans-serif;
  color: #4cd7a9;
  font-size: 30px;
}
section {
  padding: 190px;
  padding-bottom: 0;
}
.line {
  width: 65%;
  height: 2px;
  border-top: 2px solid #4cd7a9;
  margin: 0;
}
.row {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
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
.rowlogos img:hover {
  filter: grayscale(1);
}
@media screen and (max-width: 480px) {
  section {
    margin: 0 6%;
    padding: 0;
  }
  .container {
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
  }
  .line {
    width: 50%;
  }
  .image {
    position: relative;
    top: initial;
    width: 270px;
    height: 320px;
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
