<template>
  <section id="work">
    <div class="container">
      <div class="text">
        <div class="row">
          <h1>Onde Trabalho</h1>
          <div class="line"></div>
        </div>
        <div class="content">
          <a href="https://appmax.com.br/" target="blank"
            ><span class="greentxt">Appmax</span></a
          >
          <br />
          <p>
            <span class="hoverable">Fevereiro</span>
            <span class="hoverable"> 2022</span>
            <span class="hoverable"> - </span>
            <span class="hoverable">Atual</span>
          </p>
          <p>
            <span class="hoverable">Estagiário</span>
            <span class="hoverable"> de </span>
            <span class="hoverable">Desenvolvimento</span>
          </p>
          <p>
            <span class="hoverable">Tecnologias</span>
            <span class="hoverable"> utilizadas:</span>
            <span class="hoverable"> PHP,</span>
            <span class="hoverable"> Laravel,</span>
            <span class="hoverable"> Vue.js,</span>
            <span class="hoverable"> Git</span>
            <span class="hoverable"> e</span>
            <span class="hoverable"> Docker.</span>
          </p>
        </div>
      </div>
      <div class="text">
        <div class="row">
          <h1>Outros Projetos</h1>
          <div class="line"></div>
        </div>
        <div class="projects">
          <div class="card">
            <img src="imgs/1.png" alt="Projeto1" />
            <div class="icons">
              <a
                href="https://confident-poitras-58ad60.netlify.app/"
                target="blank"
                ><ion-icon name="link-outline"></ion-icon
              ></a>
              <a href="#work"><ion-icon name="logo-github"></ion-icon></a>
            </div>
          </div>
          <div class="card">
            <img src="imgs/3.png" alt="Projeto2" />
            <div class="icons">
              <a href="https://boring-jones-273a0b.netlify.app/" target="blank"
                ><ion-icon name="link-outline"></ion-icon
              ></a>
              <a
                href="https://github.com/FelipeEvaldtCarvalho/buscadorgithub"
                target="blank"
                ><ion-icon name="logo-github"></ion-icon
              ></a>
            </div>
          </div>
          <div class="card">
            <img src="imgs/2.png" alt="Projeto3" />
            <div class="icons">
              <a
                href="https://tender-wozniak-5da602.netlify.app/"
                target="blank"
                ><ion-icon name="link-outline"></ion-icon
              ></a>
              <a
                href="https://github.com/FelipeEvaldtCarvalho/todo/"
                target="blank"
                ><ion-icon name="logo-github"></ion-icon
              ></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "WorkComponent",
};
</script>

<style scoped>
.content a {
  font-family: "Play", sans-serif;
  font-size: 26px;
  color: #4cd7a9;
  text-decoration: none;
}
p {
  font-family: "Play", sans-serif;
  font-size: 25px;
  color: white;
}
h1 {
  font-family: "Montserrat", sans-serif;
  color: #4cd7a9;
  font-size: 2rem;
}
section {
  padding: 100px 190px;
}
.line {
  flex-grow: 1;
  height: 2px;
  border-top: 2px solid #4cd7a9;
  margin: 0;
}
.row {
  display: flex;
  width: 65%;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
.content {
  display: flex;
  flex-direction: column;
  padding: 15px 0;
  margin: 15px;
}
.greentxt {
  color: #4cd7a9;
}
.hoverable {
  transition: 0.5s;
}
.hoverable:hover {
  color: #4cd7a9;
}
.text {
  padding: 20px;
  padding-bottom: 60px;
}
.projects {
  padding-top: 50px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 30%;
}
.card img {
  width: 100%;
  box-shadow: 0 0 5px #4cd7a9;
  border-radius: 5px;
  transition: 0.6s;
}
.card img:hover {
  box-shadow: 0 0 15px #4cd7a9;
}
.icons {
  padding: 15px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 100%;
  font-size: 30px;
}
.icons a {
  color: white;
  transition: 0.5s;
}
.icons a:hover {
  color: #4cd7a9;
}
@media screen and (max-width: 820px) and (min-width: 481px) {
  section {
    padding: 0;
    margin: 20% 12%;
  }
  .text {
    padding: 0;
    margin-bottom: 12%;
  }
  .row {
    width: 100%;
  }
  .projects {
    padding-top: 3rem;
    flex-direction: column;
  }
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 80%;
    margin-bottom: 2rem;
  }
}
@media screen and (max-width: 480px) {
  section {
    padding: 0;
    margin: 0 6%;
  }
  .text {
    padding: 0;
  }
  .row {
    width: 100%;
  }
  h1 {
    font-size: 1.6rem;
  }
  .line {
    width: 30%;
  }
  .container {
    margin-top: 8rem;
  }
  .content {
    padding: 0;
    margin: 2rem 0;
  }
  .content a {
    font-size: 1.3rem;
  }
  p {
    font-size: 1.1rem;
  }
  .projects {
    padding-top: 3rem;
    flex-direction: column;
  }
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 80%;
    margin-bottom: 2rem;
  }
}
</style>
