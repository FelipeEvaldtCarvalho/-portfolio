<template>
  <section id="contact">
    <div class="text">
      <div>
        <div class="row">
          <h1>Entre em Contato</h1>
          <div class="line"></div>
        </div>
        <div class="content">
          <p>
            Sinta-se a vontade para entrar em contato, sua mensagem será muito
            bem vinda!
          </p>
        </div>
      </div>
      <lottie-player
        src="/imgs/rocket.json"
        background="transparent"
        speed="1"
        loop
        autoplay
      ></lottie-player>
    </div>
    <div class="form">
      <form ref="form">
        <div class="form-row">
          <label ref="nameLabel" for="name">Nome</label>
          <input
            ref="nameInput"
            @focus="nameFocus"
            @focusout="nameFocusOut"
            type="text"
            v-model="name"
            name="name"
            autocomplete="nope"
          />
        </div>
        <div class="row-validation">
          <span class="error" v-if="v$.name.$error"
            ><ion-icon name="alert-circle-sharp"></ion-icon>
            <p>O Campo nome é obrigatório!</p></span
          >
        </div>
        <div class="form-row">
          <label ref="emailLabel" for="email">Email</label>
          <input
            type="email"
            name="email"
            v-model="email"
            ref="emailInput"
            @focus="emailFocus"
            @focusout="emailFocusOut"
            autocomplete="nope"
          />
        </div>
        <div class="row-validation">
          <span
            class="error"
            v-if="v$.email.required.$invalid && v$.email.$error"
            ><ion-icon name="alert-circle-sharp"></ion-icon>
            <p>O Campo Email é obrigatório!</p></span
          >
          <span class="error" v-if="v$.email.email.$invalid"
            ><ion-icon name="alert-circle-sharp"></ion-icon>
            <p>Insira um Email válido!</p></span
          >
        </div>
        <div class="form-row">
          <label ref="msgLabel" for="message">Mensagem</label>
          <textarea
            ref="msgInput"
            @focus="msgFocus"
            @focusout="msgFocusOut"
            name="message"
            v-model="msg"
            id="message"
            cols="10"
            rows="2"
            autocomplete="nope"
          ></textarea>
        </div>
        <div class="row-validation">
          <span class="error" v-if="v$.msg.$error"
            ><ion-icon name="alert-circle-sharp"></ion-icon>
            <p>O Campo Mensagem é obrigatório!</p></span
          >
        </div>
        <div class="row-btn">
          <button class="btn" @click.prevent="sendEmail">Enviar</button>
        </div>
      </form>
    </div>
  </section>
</template>
<script>
import { useVuelidate } from "@vuelidate/core";
import { required, email } from "@vuelidate/validators";
import emailjs from "@emailjs/browser";

export default {
  name: "ContactComponent",
  components: {},
  data() {
    return {
      name: "",
      email: "",
      msg: "",
      isModalVisible: false,
      contactTxt: null,
      toast: false,
      toastType: null,
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },

    nameFocus() {
      this.$refs.nameLabel.style.top = 0;
      this.$refs.nameLabel.style.left = 0;
      this.$refs.nameLabel.style.color = "#4cd7a9";
      this.$refs.nameInput.style.borderBottom = "3px #4cd7a9 solid";
    },
    nameFocusOut(el) {
      if (!el.target.value) {
        this.$refs.nameLabel.style.top = "2rem";
        this.$refs.nameLabel.style.left = "1rem";
        this.$refs.nameLabel.style.color = "#808080";
        this.$refs.nameInput.style.borderBottom = "3px #808080 solid";
      }
      return;
    },
    emailFocus() {
      this.$refs.emailLabel.style.top = 0;
      this.$refs.emailLabel.style.left = 0;
      this.$refs.emailLabel.style.color = "#4cd7a9";
      this.$refs.emailInput.style.borderBottom = "3px #4cd7a9 solid";
    },
    emailFocusOut(el) {
      if (!el.target.value) {
        this.$refs.emailLabel.style.top = "2rem";
        this.$refs.emailLabel.style.left = "1rem";
        this.$refs.emailLabel.style.color = "#808080";
        this.$refs.emailInput.style.borderBottom = "3px #808080 solid";
      }
      return;
    },
    msgFocus() {
      this.$refs.msgLabel.style.top = 0;
      this.$refs.msgLabel.style.left = 0;
      this.$refs.msgLabel.style.color = "#4cd7a9";
      this.$refs.msgInput.style.borderBottom = "3px #4cd7a9 solid";
    },
    msgFocusOut(el) {
      if (!el.target.value) {
        this.$refs.msgLabel.style.top = "2rem";
        this.$refs.msgLabel.style.left = "1rem";
        this.$refs.msgLabel.style.color = "#808080";
        this.$refs.msgInput.style.borderBottom = "3px #808080 solid";
      }
      return;
    },
    sendEmail() {
      this.v$.$validate();
      if (this.v$.name.$error || this.v$.email.$error || this.v$.msg.$error) {
        return;
      }
      try {
        emailjs.sendForm(
          process.env.VUE_APP_EMAILJS_SERVICE_ID,
          process.env.VUE_APP_EMAILJS_TEMPLATE_ID,
          this.$refs.form,
          process.env.VUE_APP_EMAILJS_USER_ID
        );
        this.name = "";
        this.email = "";
        this.msg = "";
        this.$emit("close");
        return this.$emit("toast", "success");
      } catch (error) {
        return this.$emit("toast", "fail");
      }
    },
  },
  setup() {
    return { v$: useVuelidate() };
  },
  validations() {
    return {
      name: { required },
      email: { email, required },
      msg: { required },
    };
  },
};
</script>

<style scoped>
section {
  padding: 150px 190px;
  display: flex;
  gap: 3rem;
}
.text {
  display: flex;
  flex-direction: column;
  width: 50%;
}
.row {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
p {
  font-family: "Montserrat", sans-serif;
  font-weight: 200;
  font-size: 25px;
  color: white;
}
h1 {
  font-family: "Montserrat", sans-serif;
  font-weight: 400;
  color: #4cd7a9;
  font-size: 30px;
}
.line {
  flex-grow: 1;
  height: 2px;
  border-top: 2px solid #4cd7a9;
  margin: 0;
}
.content {
  display: flex;
  flex-direction: column;
  padding: 15px 0;
  margin: 15px;
}
.btn {
  width: 150px;
  margin: auto;
  margin-top: 4rem;
}
.form {
  display: flex;
  flex-direction: column;
  width: 50%;
  padding: 0 2rem;
  padding-top: 4rem;
  background-color: rgb(16, 16, 16);
  height: auto;
  border-radius: 1rem;
}
.form-row {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
}
.form-row label {
  pointer-events: none;
  font-size: 1.2rem;
  font-family: "Montserrat", sans-serif;
  font-weight: 400;
  color: #808080;
  position: relative;
  top: 2rem;
  left: 1rem;
  transition: all 0.6s ease;
}
.form-row input,
.form-row textarea {
  font-size: 1.2rem;
  padding: 0.5rem 1rem;
  background-color: transparent;
  font-family: "Montserrat", sans-serif;
  border: none;
  font-weight: 400;
  color: #fff;
  border-bottom: 3px #808080 solid;
  transition: all 0.6s ease;
  resize: none;
}
.form-row input:focus,
.form-row textarea:focus {
  outline: none;
}
.row-btn {
  display: flex;
  width: 100%;
}
.error {
  margin-bottom: 0.5rem;
  display: flex;
  gap: 0.5rem;
  color: #ffb560;
  font-size: 1rem;
  align-items: center;
}
.error p {
  color: #ffb560;
  font-size: 1rem;
}
.error ion-icon {
  font-size: 1.5rem;
}
lottie-player {
  margin-top: 5rem;
  width: 100%;
  height: 350px;
  transform: rotate(45deg);
}
@media screen and (max-width: 1130px) {
  section {
    display: flex;
    flex-direction: column;
  }
  .text {
    display: flex;
    flex-direction: row;
    width: 100%;
  }
  lottie-player {
    margin-top: 0;
    width: auto;
    height: 100%;
    transform: rotate(45deg);
  }
  .form {
    width: 100%;
    padding: 4rem 2rem;
  }
}
@media screen and (max-width: 820px) and (min-width: 481px) {
  section {
    height: auto;
    padding: 0;
    margin: 20% 12%;
  }
  .row {
    width: 100%;
  }
  .content {
    padding: 0;
    margin: 2rem 0;
  }
  .btn {
    width: 80%;
    margin: 5rem auto;
  }
  .text {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  lottie-player {
    margin-top: 0;
    width: auto;
    height: 350px;
    margin: auto;
    transform: rotate(45deg);
  }
}

@media screen and (max-width: 480px) {
  section {
    height: auto;
    padding: 0;
    margin: 20% 6%;
  }
  .row {
    width: 100%;
  }
  p {
    font-size: 1.2rem;
    max-width: 100%;
  }
  h1 {
    font-size: 1.6rem;
  }
  .content {
    padding: 0;
    margin: 2rem 0;
  }
  .btn {
    width: 80%;
    margin: 5rem auto;
  }
  .text {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  lottie-player {
    margin-top: 0;
    width: auto;
    height: 250px;
    margin: auto;
    transform: rotate(45deg);
  }
}
</style>
