<template>
  <div id ="app">
    <Calculator />
  </div>
  <div>
    <div>{{ expression }}</div>
    <form @submit.prevent="calculate">
      <div class="calculator">
        <button class= "btn operator" type="button" @click.stop="expression += '+'">+</button>
        <button class= "btn operator" type="button" @click.stop="expression += '-'">-</button>
        <button class= "btn operator" type="button" @click.stop="expression += '*'">*</button>
        <button class= "btn operator" type="button" @click.stop="expression += '/'">/</button>
      
      
        <button class= "btn"  type="button" @click.stop="expression += '.'">.</button>
        <button class= "btn" type="button" @click.stop="expression += '9'">9</button>
        <button class= "btn"  type="button" @click.stop="expression += '8'">8</button>
        <button class= "btn"  type="button" @click.stop="expression += '7'">7</button>
      
      
        <button class= "btn"  type="button" @click.stop="expression += '6'">6</button>
        <button class= "btn"  type="button" @click.stop="expression += '5'">5</button>
        <button class= "btn"  type="button" @click.stop="expression += '4'">4</button>
        <button class= "btn" type="button" @click.stop="expression += '3'">3</button>
      
     
        <button class= "btn"  type="button" @click.stop="expression += '2'">2</button>
        <button class= "btn"  type="button" @click.stop="expression += '1'">1</button>
        <button class= "btn zero"  type="button" @click.stop="expression += '0'">0</button>
        <button class= "btn operator"  type="submit">=</button>
      </div>
      <div>
        <button type="button" @click.stop="expression = ''">Clear</button>
      </div>
    </form>
  </div>
</template>

<script>
  import { evaluate } from "mathjs";
export default {
  name: "App",
  data() {
    return {
      expression: "",
    };
  },
  methods: {
    calculate() {
      this.expression = evaluate(this.expression);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.calculator { 
  margin: 0 auto;
  width: 300px;
  height: 300px;
  font-size: 40px;
  justify-content: center;
  align-items: center;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  cursor: pointer;
}



.operator {
  background-color: skyblue;
  color: white;
}

.btn { 
  height: 50px;
}





</style>



