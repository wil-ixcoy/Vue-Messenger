<!--modal que aparece para confirmar si se quiere borrar o no la sala-->

<template>
  <div class="modal">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <h3 class="subtitle is-size-4 is-marginless">Confirmation</h3>
      </header>
      <section class="modal-card-body">
          <!--mensaje recibido como props-->
        <h3 class="subtitle has-text-centered">{{ message }}</h3>
      </section>
      <footer class="modal-card-foot buttons is-right">
        <!--se emite un evento que recibe el componente padre updateRoom-->
        <button @click="$emit('confirm')" class="button" :class="actionClass">
          Confirm
        </button>
        <!--se emite un evento que recibe el componente padre updateRoom-->
        <button @click="$emit('cancel')" class="button">Cancel</button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: "ConfirmationModalComponent",
  props: {
      //recibe un mensaje de tipo strin y requerido
    message: {
      type: String,
      required: true,
    },
    //accion de la clase recibida como props
    actionClass: {
      type: String,
      default: "is-danger",
    },
  },
};
</script>

<style scoped>
.modal {
  display: block;
}
</style>