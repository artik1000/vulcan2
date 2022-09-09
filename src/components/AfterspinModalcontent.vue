<template>
<div class="modal-container">
  <div class="modal-header">
    <h1>Glünckwunsch!</h1>
    <h1 class="second-header">Ihr Gewinn ist</h1>
  </div>
  <div class="modal-main">
    <div class="modal-main__pize-headers">
        <h2>1.500 EUR UND</h2>
        <h2>270 FREISPIELE</h2>
    </div>
    <div class="modal-main__money-img" loading="lazy">
    </div>
    <div>
      <slot></slot>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "afterspin-modalcontent"
}
</script>

<style lang="scss" scoped>
h1 {
  color:#faae2e;
  font-weight: bold;
  line-height: 35px;
  font-size: 35px;
  margin: 0;
  padding: 0;
  &.second-header {
    letter-spacing: 1px;
  }
}
.modal-container{
  display: flex;
  flex-direction: column;
  box-shadow: #5c4c12;
}
.modal-header {
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
  background: #0b4aa5;
  border-top: 1px solid #5670a1;
  border-right: 1px solid #5670a1;
  border-left: 1px solid #5670a1;
  padding: 20px;
}
.modal-main{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  padding-bottom: 30px;
  .modal-main__pize-headers{
    color: #c12224;
    padding: 10px 10px 0 10px;
    h2{
      line-height: 32px;
      font-size: 32px;
      font-weight: bold;
      margin: 0;
      padding: 0;
    }
  }
  .modal-main__money-img{
    background-image: url("@/assets/money_icon.png");
    background-repeat: no-repeat;
    background-size: 100%;
    height: 75px;
    width: 150px;
  }
}
</style>