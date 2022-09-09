<template>
  <button class="modal-main__button">
    ERHALTEN
  </button>
</template>

<script>
export default {
  name: "modal-button"
}
</script>

<style scoped>
.modal-main__button {
  color: white;
  background: #3dad39;
  /*box-shadow-bottom: #2f8b2d;*/
  font-weight: bold;
  font-size: 30px;
  width: max-content;
  padding: 20px 40px 30px 40px;
  border: 1px solid transparent;
  border-radius: 6px;
  box-shadow: 0px -13px 0px -5px #2f8b2d inset;
}
.modal-main__button:hover{
  background: #2f8b2d;
  box-shadow: 0px -13px 0px -5px #004400 inset;
}
</style>