<template>
  <footer>
    <div>
      <p>
        <ion-icon name="rocket-outline"></ion-icon>&nbsp; Desenvolvido por
        Felipe Carvalho
      </p>
    </div>
    <ul>
      <li>
        <a href="https://github.com/FelipeEvaldtCarvalho/" target="blank"
          ><ion-icon class="link-icon" name="logo-github"></ion-icon
        ></a>
      </li>
      <li>
        <a
          href="https://www.linkedin.com/in/felipe-evaldt-carvalho-9ab1461aa/"
          target="blank"
          ><ion-icon class="link-icon" name="logo-linkedin"></ion-icon
        ></a>
      </li>
      <li>
        <a href="https://wa.me/5551993871466" target="blank"
          ><ion-icon class="link-icon" name="logo-whatsapp"></ion-icon
        ></a>
      </li>
    </ul>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
footer {
  font-family: "Play", sans-serif;
  font-size: 19px;
  height: 100px;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  justify-content: center;
  color: #4cd7a9;
  margin-bottom: 2rem;
}
p {
  display: flex;
  align-items: center;
}
ion-icon {
  font-size: 25px;
  color: #4cd7a9;
}
ul {
  display: none;
}
@media screen and (max-width: 480px) {
  ul {
    display: flex;
    align-items: center;
    justify-content: center;
    list-style: none;
    gap: 3rem;
    margin-bottom: 2rem;
  }
  footer {
    font-size: 15px;
  }
  ion-icon {
    font-size: 20px;
  }
  .link-icon {
    font-size: 40px;
  }
}
</style>
