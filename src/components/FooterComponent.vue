<template>
  <footer>
    <p>
      <ion-icon name="rocket-outline"></ion-icon>&nbsp; Desenvolvido por Felipe
      Carvalho
    </p>
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
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #4cd7a9;
}
p {
  display: flex;
  align-items: center;
}
ion-icon {
  font-size: 25px;
  color: #4cd7a9;
}
@media screen and (max-width: 480px) {
  footer {
    font-size: 15px;
  }
  ion-icon {
    font-size: 20px;
  }
}
</style>
