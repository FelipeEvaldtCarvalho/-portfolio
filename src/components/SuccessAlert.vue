<template>
  <div>
    <div class="toast-msg success" v-if="alertType === success">
      <ion-icon name="checkmark-circle-sharp"></ion-icon>
      <p>Mensagem enviada com sucesso!</p>
    </div>
    <div class="toast-msg fail" v-if="alertType === fail">
      <ion-icon name="alert-circle-sharp"></ion-icon>
      <p>Falha ao enviar sua mensagem!</p>
    </div>
  </div>
</template>
<script>
export default {
  name: "SuccessAlert",
  data() {
    return {
      fail: "fail",
      success: "success",
    };
  },
  props: {
    alertType: String,
  },
};
</script>
<style scoped>
.toast-msg {
  position: fixed;
  display: flex;
  align-items: center;
  top: 0;
  right: 0;
  margin: 5rem;
  padding: 1rem;
  font-size: 1.2rem;
  z-index: 10001;
  border-radius: 15px;
  gap: 0.5rem;
}
.success {
  color: #1e5f1e;
  background-color: #d4ffd4;
}
.fail {
  color: #780000;
  background-color: #ffc85b;
}
.toast-msg ion-icon {
  font-size: 1.5rem;
}
</style>
