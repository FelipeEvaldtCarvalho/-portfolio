<template>
  <div class="modal-window">
    <div class="modal">
      <div class="close-btn">
        <a @click.prevent="close"
          ><ion-icon name="close-circle-outline"></ion-icon
        ></a>
        <h1>Deixe seu recado</h1>
      </div>
      <form action="">
        <div class="row">
          <label for="name">Nome</label>
          <input type="text" />
        </div>
        <div class="row">
          <label for="email">Email</label>
          <input type="email" />
        </div>
        <div class="row">
          <label for="message">Mensagem</label>
          <textarea name="message" id="message" cols="30" rows="10"></textarea>
        </div>
        <div class="row-btn">
          <input
            @click.prevent="close"
            class="btn"
            type="button"
            value="Enviar"
          />
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalComponent",
  methods: {
    close() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal-window {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10000;
}
.modal {
  height: auto;
  width: 90%;
  border-radius: 15px;
  background-color: #242424;
  overflow-x: auto;
  display: flex;
  flex-direction: column;
  color: #4cd7a9;
  font-family: "Play", sans-serif;
  font-size: 22px;
}
form {
  display: flex;
  flex-direction: column;
  padding: 25px;
  width: 100%;
}
.row {
  display: flex;
  justify-content: space-between;
  margin: 10px 0;
}
input,
textarea {
  width: 75%;
  resize: none;
  border-radius: 5px;
}
input {
  font-family: "Montserrat", sans-serif;
  font-size: 20px;
  padding: 3px 5px;
}
input:focus {
  outline-color: #4cd7a9;
}
textarea:focus {
  outline-color: #4cd7a9;
}
.row-btn {
  display: flex;
  justify-content: center;
  padding: 30px;
}
.row-btn input {
  font-family: "Play", sans-serif;
  width: auto;
  padding: 5px 25px;
}
.close-btn {
  width: 100%;
  display: flex;
  padding: 15px;
  flex-direction: row-reverse;
  justify-content: space-between;
}
.close-btn h1 {
  font-size: 25px;
}
a {
  font-size: 30px;
  color: rgb(248, 144, 126);
  transition: 0.9s;
  cursor: pointer;
}
a:hover {
  color: tomato;
}
@media screen and (max-width: 820px) {
  .modal {
    height: auto;
    width: 90%;
  }
  .row {
    flex-direction: column;
  }
  form {
    padding: 6%;
  }
  input,
  textarea {
    width: 100%;
  }
}
</style>
