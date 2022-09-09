<template>
  <div class="roulette-button-background">
    <button
        class="roulette-button"
        :class="startSpin ? 'roulette-button_spinning' : 'roulette-button_not-spinning'"
        @click="$emit('startSpin')"
    >
      Spin
    </button>
  </div>
</template>

<script>
export default {
  name: "roulette-button",
  props: {
    startSpin: {
      type: Boolean,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.roulette-button-background {
  background: #e4e2e5;
  padding: 10px;
  height: 130px;
  width: 130px;
  border-radius: 50% 50% 0% 50%;
  transform: rotate(-45deg);
}
.roulette-button {
  transform: rotate(45deg);
  box-sizing: border-box;
  height: 110px;
  width: 110px;
  border: 0.0001px solid transparent;
  border-radius: 50%;
  color: white;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 35px;
}
.roulette-button_not-spinning{
  /*first state*/
  background: radial-gradient(circle farthest-side at 30px 30px,#00a724 15%, #006219 75%);
  box-shadow: 0px -4px 0px 1px #004400 inset;
}
.roulette-button_not-spinning:hover{
  /*third state*/
  background: radial-gradient(circle farthest-side at 30px 30px,#007309 15%, #003c05 75%);
  box-shadow: 0px -4px 0px 1px #002100 inset;
}
.roulette-button_spinning{
  /*second state*/
  background: radial-gradient(circle farthest-side at 30px 30px,#00d51c 15%, #007411 75%);
  box-shadow: 0px -4px 0px 1px #005200 inset;
}
@media screen and (max-width: 480px) {
  .roulette-button-background {
    background: #e4e2e5;
    padding: 7px;
    height: 90px;
    width: 90px;
    border-radius: 50% 50% 0% 50%;
    transform: rotate(-45deg);
  }
  .roulette-button {
    transform: rotate(45deg);
    box-sizing: border-box;
    height: 75px;
    width: 75px;
    border: 0.0001px solid transparent;
    border-radius: 50%;
    color: white;
    font-weight: bold;
    text-transform: uppercase;
    font-size: 25px;
  }
}
</style>