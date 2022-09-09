<template>
 <div class="roulette">
   <div class="centred">
     <roulette-button
         :startSpin="startSpin"
         @startSpin="spinStart"
     />
   </div>
   <div
       class="roulette-pie"
       :class="startSpin === false ? 'roulette-pie_cycled' : 'roulette-pie_spinning'"
   >
     <div class="roulette-pie__first-piece">
       <p class="noch-einmal">NOCH <br>
         EINMAL</p>
     </div>
     <div class="roulette-pie__second-piece">
       <p class="leer">LEER</p>
     </div>
     <div class="roulette-pie__third-piece">
       <p class="prize main-prize">1.500 € <br>
<!--       270 FREISPIELE--></p>
     </div>
     <div class="roulette-pie__fourth-piece">
       <p class="noch-einmal">NOCH <br>
         EINMAL</p>
     </div>
     <div class="roulette-pie__fifth-piece">
       <p class="leer">LEER</p>
     </div>
     <div class="roulette-pie__sixth-piece">
       <p class="prize additional-prize">1.000 € <br>
<!--       180 FREISPIELE--></p>
     </div>
   </div>
   <modal-window v-model:show="dialogVisible">
     <afterspin-modalcontent>
       <modal-button @click="spinEnd"/>
     </afterspin-modalcontent>
   </modal-window>
 </div>
</template>

<script>
import RouletteButton from "@/components/RouletteButton";
import ModalWindow from "@/components/ModalWindow";
import AfterspinModalcontent from "@/components/AfterspinModalcontent";
import ModalButton from "@/components/ModalButton";
export default {
  name: "roulette-module",
  components: {ModalButton, AfterspinModalcontent, ModalWindow, RouletteButton},
  data () {
    return {
      startSpin: false,
      dialogVisible: false
    }
  },
  methods: {
    spinStart () {
      this.startSpin = true
      setTimeout(() => {
        this.dialogVisible = true
      },3100)
    },
    spinEnd () {
      this.startSpin = false
      this.dialogVisible = false
    }
  },
}
</script>

<style lang="scss" scoped>
/*
500
500
275
97
*/
.roulette{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}
.centred {
  position: absolute;
  top:0;
  left:0;
  bottom:0;
  right:0;
  margin: auto;
  z-index: 999;
  width: fit-content;
  height: fit-content;
}
.roulette-pie_cycled{
  animation: miniSpin 3s infinite linear;
}
.roulette-pie_spinning{
  animation: finalSpin 3s linear forwards;
}
@keyframes finalSpin {
  0% {
    transform: rotate(0deg);
  }
  40% {
    transform: rotate(360deg);
  }
  70% {
    transform: rotate(700deg);
  }
  80% {
    transform: rotate(730deg);
  }
  100% {
    transform: rotate(710deg);
  }
}
@keyframes miniSpin {
  0% {
    transform: rotate(-60deg);
  }
  50% {
    transform: rotate(-57deg);
  }
  100% {
    transform: rotate(-60deg);
  }
}
@media screen and (min-width: 767px) {
  .roulette-pie{
    width: 500px;
    height: 500px;
    border-radius: 50%;
    border: 15px solid rgba(0, 0, 0, .5);
    position: relative;
    overflow: hidden;

    div{
      height: 50%;
      width: 275px;
      position: absolute;
      clip-path: polygon(100% 0 , 50% 100% , 0 0 );
      transform: translateX(-50%);
      transform-origin: bottom;
      text-align: center;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      font-weight: bold;
      font-family: sans-serif;
      color: #fff;
      left: 97px;
    }
    .roulette-pie__first-piece{
      background-color: #a552e5;
      left: 50%;
    }
    .roulette-pie__second-piece{
      background-color: #00b08f;
      transform: rotate(60deg);
    }
    .roulette-pie__third-piece{
      background-color: #ffb100;
      transform:rotate(120deg);
    }
    .roulette-pie__fourth-piece{
      background-color: #008ac8;
      transform: rotate(180deg);
    }
    .roulette-pie__fifth-piece{
      background-color: #a11a3d;
      transform: rotate(240deg);
    }
    .roulette-pie__sixth-piece{
      background-color: #2145a2;
      transform: rotate(300deg);
    }
    .leer{
      margin-bottom: 120px;
      font-size: 35px;
    }
    .noch-einmal{
      margin-bottom: 100px;
      font-size: 25px;
    }
    .prize{
      margin-bottom: 100px;
      font-size: 35px;
      line-height: 23px;
    }
    .main-prize::after{
      content: "270 FREISPIELE";
      font-size: 14px;
    }
    .additional-prize::after{
      content: "180 FREISPIELE";
      font-size: 14px;
      letter-spacing: 0.5px;
    }
    p {
      transform: rotate(-90deg);
      text-align: center;
    }
  }
}
@media screen and (max-width: 480px) {
  .roulette-pie{
    width: 350px;
    height: 350px;
    border-radius: 50%;
    border: 15px solid rgba(0, 0, 0, .5);
    position: relative;
    overflow: hidden;

    div{
      height: 50%;
      width: 190px;
      position: absolute;
      clip-path: polygon(100% 0 , 50% 100% , 0 0 );
      transform: translateX(-50%);
      transform-origin: bottom;
      text-align: center;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      font-weight: bold;
      font-family: sans-serif;
      color: #fff;
      left: 65px;
    }
    .roulette-pie__first-piece{
      background-color: #a552e5;
      left: 50%;
    }
    .roulette-pie__second-piece{
      background-color: #00b08f;
      transform: rotate(60deg);
    }
    .roulette-pie__third-piece{
      background-color: #ffb100;
      transform:rotate(120deg);
    }
    .roulette-pie__fourth-piece{
      background-color: #008ac8;
      transform: rotate(180deg);
    }
    .roulette-pie__fifth-piece{
      background-color: #a11a3d;
      transform: rotate(240deg);
    }
    .roulette-pie__sixth-piece{
      background-color: #2145a2;
      transform: rotate(300deg);
    }
    .leer{
      margin-bottom: 90px;
      font-size: 23px;
    }
    .noch-einmal{
      margin-bottom: 50px;
      font-size: 15px;
    }
    .prize{
      margin-bottom: 90px;
      font-size: 23px;
      line-height: 10px;
    }
    .main-prize::after{
      content: "270 FREISPIELE";
      font-size: 9px;
    }
    .additional-prize::after{
      content: "180 FREISPIELE";
      font-size: 9px;
      letter-spacing: 0.3px;
    }
    p {
      transform: rotate(-90deg);
      text-align: center;
    }
  }
}
@media screen and (max-width: 320px) {
  .roulette-pie{
    width: 300px;
    height: 300px;
    border-radius: 50%;
    border: 15px solid rgba(0, 0, 0, .5);
    position: relative;
    overflow: hidden;

    div{
      height: 50%;
      width: 170px;
      position: absolute;
      clip-path: polygon(100% 0 , 50% 100% , 0 0 );
      transform: translateX(-50%);
      transform-origin: bottom;
      text-align: center;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      font-weight: bold;
      font-family: sans-serif;
      color: #fff;
      left: 49px;
    }
    .roulette-pie__first-piece{
      background-color: #a552e5;
      left: 50%;
    }
    .roulette-pie__second-piece{
      background-color: #00b08f;
      transform: rotate(60deg);
    }
    .roulette-pie__third-piece{
      background-color: #ffb100;
      transform:rotate(120deg);
    }
    .roulette-pie__fourth-piece{
      background-color: #008ac8;
      transform: rotate(180deg);
    }
    .roulette-pie__fifth-piece{
      background-color: #a11a3d;
      transform: rotate(240deg);
    }
    .roulette-pie__sixth-piece{
      background-color: #2145a2;
      transform: rotate(300deg);
    }
    .leer{
      margin-bottom: 70px;
      font-size: 20px;
    }
    .noch-einmal{
      margin-bottom: 50px;
      font-size: 15px;
    }
    .prize{
      margin-bottom: 70px;
      font-size: 20px;
      line-height: 10px;
    }
    .main-prize::after{
      content: "270 FREISPIELE";
      font-size: 8px;
    }
    .additional-prize::after{
      content: "180 FREISPIELE";
      font-size: 8px;
      letter-spacing: 0.3px;
    }
    p {
      transform: rotate(-90deg);
      text-align: center;
    }
  }
}
</style>