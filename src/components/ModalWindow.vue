<template>
  <div class="dialog" v-if="show" @click.stop="hideDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import toggleMixin from '@/mixins/toggleMixin'
export default {
  name: "modal-window",
  mixins: [toggleMixin]
}
</script>

<style lang="scss" scoped>
.dialog{
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
  z-index: 999999999;
}
@media screen and (min-width: 768px){
  .dialog__content{
    /*margin: auto 10px auto 10px;*/
    margin: auto;
    border-radius: 6px;
    min-height: 50px;
    min-width: 300px;
    background: #eff1f4;
    width: max-content;
  }
}
@media screen and (max-width: 767px){
  .dialog__content{
    margin: auto 10px auto 10px;
    border-radius: 6px;
    min-height: 50px;
    min-width: 300px;
    background: #eff1f4;
    width: 100%;
  }
}
</style>