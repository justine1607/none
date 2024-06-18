<script>
export default {
  data(){
    return{
      inputValue: "",
      add:""
    };
  },
  computed: {
    stringInputValue() {
      return String(this.inputValue);
    }
  },
  methods:{
    number(num){
      console.log('number clicked')
      this.inputValue += num
    },
    clear(clean){
      console.log('cleared')
      this.inputValue  = clean
    },
    divide(operator){
      this.inputValue += operator
    },
    times(operator){
      this.inputValue += operator
    },
    minus(operator){
      this.inputValue += operator
    },
    dot(dot){
      this.inputValue += dot
    },
    plus(operator){
      this.inputValue += operator
    },
    deleteNum(){
      console.log('deleted');
      this.inputValue = this.stringInputValue.slice(0,-1)
    },
    equals() {
      const result = eval(this.stringInputValue);
      // Convert the result to a string before assigning it to inputValue
      this.inputValue = String(result);
    }
  }
}

</script>

<template>

  <div class="container">
    <div class="calc-grid">
      <div class="headerCalc">
        <h1>calculator</h1>
      </div>
      <div class="calculator">
        <input  v-model="inputValue" class="add" type="text" placeholder="0">

        <div class="calculator-grid">
          <button class="calc-button clearAll" @click="clear('')">AC</button>
          <button class="calc-button seven"  @click="number(7)">7</button>
          <button class="calc-button eight" @click="number(8)">8</button>
          <button class="calc-button nine" @click="number(9)">9</button>
          <button class="calc-button first-rows" @click="divide('/')">/</button>

          <button class="calc-button four" @click="number(4)">4</button>
          <button class="calc-button" @click="number(5)">5</button>
          <button class="calc-button" @click="number(6)">6</button>
          <button class="calc-button" @click="times('*')">*</button>

          <button class="calc-button" @click="number(1)">1</button>
          <button class="calc-button" @click="number(2)">2</button>
          <button class="calc-button" @click="number(3)">3</button>
          <button class="calc-button" @click="minus('-')">-</button>

          <button class="calc-button" @click="number(0)">0</button>
          <button class="calc-button" @click="dot('.')">.</button>
          <button class="calc-button" @click="equals">=</button>
          <button class="calc-button" @click="plus('+')">+</button>
          <button class="calc-button delete" @click="deleteNum">delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
body{

}
.container {
  margin: 0 auto;
  max-width: 1320px;
  width: 100%;
}

.calculator {
  background: white;
  grid-column: span 6;
  margin: 0 auto;
  max-width: 400px;
  border-radius: 5px;
  padding: 20px;
}
.calculator-grid{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 3px;
  max-width: 1390px;
  margin-inline: auto;
}
.calculator input{
  font-size: 40px;
  background: none;
  border: none;
  box-shadow: none;
  width: 100%;
  border-bottom: 2px solid #222222;
  padding: 20px;
  text-align: right;margin-bottom: 10px;

}
.clearAll,.delete{
  grid-column: span 1;
  background: burlywood!important;
}
.calc-button{
  background: rgba(0,0,0,0.5);
  border: 1px solid #222222;
  padding: 20px;
  color: #282828;
  border-radius: 5px;
  font-size: 22px;
  cursor: pointer;

}
.headerCalc{
  grid-column: span 6;
  margin: 0 auto;
}
.bttNumber{
  grid-column: 1 / span 2;
}
</style>
