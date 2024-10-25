<template>
  <div class="calculator">
   
    <div class = "display">{{ current || '0' }}</div>
    <div @click="percent" class = "btn">%</div>
    <div class = "btn">CE</div>
    <div @click = "clear" class = "btn">C</div>
    <div class = "btn">X</div>
    <div class = "btn"><sup>1</sup>/<sub>x</sub></div>
    <div class = "btn">x²</div>
    <div class = "btn">²&Sqrt;x</div>
    <div class = "btn">÷</div>
    <div @click = "append('7')" class = "btn">7</div>
    <div @click = "append('8')" class = "btn">8</div>
    <div @click = "append('9')" class = "btn">9</div>
    <div class = "btn">&times;</div>
    <div @click = "append('4')" class = "btn">4</div>
    <div @click = "append('5')" class = "btn">5</div>
    <div @click = "append('6')" class = "btn">6</div>
    <div class = "btn">&minus;</div>
    <div @click = "append('1')" class = "btn">1</div>
    <div @click = "append('2')" class = "btn">2</div>
    <div @click = "append('3')" class = "btn">3</div>
    <div class = "btn">&plus;</div>
    <div @click = "sign" class = "btn">&plusmn;</div>
    <div @click = "append('0')" class = "btn">0</div>
    <div class = "btn">&comma;</div>
    <div class = "btn">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: '0',
    }
  },
  methods: {
    clear() {
      this.current = '' ;
    },
    sign() {
      this.current = this.current.charAt(0) === '-'? this.current.slice(1): `-${this.current}`;
    },
    append(number){
      // this.current = '';
      this.current = `${this.current}${number}`;
    },
    percent(){
      this.current = `${parseFloat(this.current)/100}`
    }
  }

}
</script>

<style>
.calculator {
  width: 320px;
  height: 300px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  background-color:#000000;
  text-align: center;
}

.display{
  grid-column-start: 1;
  grid-column-end: 5;
  background-color: rgb(54, 54, 54);
  font-size: 24px;
  border-radius: 2px;
  color: white;
}
.btn {
  padding: 1px;
  border: solid 0px ;
}
.btn{
  width: 100%;
  height: 100%;
  font-size: 20px;
  border-radius: 5px;
  color: white;
  background-color:rgb(54, 54, 54);
}
</style>
