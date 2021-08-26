<template>
  <div id="app">
    <Header title="SPLI TTER"/>
  
    <div class="container">

      <div class ="info">

      <!-- Input for Bill -->
      <InputBill  v-model.number="bill"/>

      <!-- Percentages -->

      <div class = "percent">
        <p style = "margin: 8px"> Select Tip % </p>
          <Button v-for="n in percentages" :key="n" :text="n" @btn-click="action(n)"/>
          <Button text="Custom"> </Button>
      </div>

      <!-- Input for Number of Persons -->
      <InputPeople v-model.number="people"/>

    </div>

    <!-- Display Reults -->
    <div class = "output">
      <Result text="Tip Amount" :result="tipAmount"/>
      <Result text="Total" :result="total"/> 

        <!-- Reset -->

    <button class="reset" @click="reset()"> RESET </button>

    </div>

    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Button from './components/Button.vue'
import InputBill from './components/InputBill.vue'
import InputPeople from './components/InputPeople.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Header,
    Button,
    InputBill,
    InputPeople,
    Result,
  },

  data(){
    return this.initialState();
  },

  methods: {
    action(n) {
      if(n === '5%') {
        this.tipAmount = this.bill * 0.05 / this.people;
        this.total= this.bill * 1.05 / this.people;
      }

      if(n === '10%') {
        this.tipAmount = this.bill * 0.10 / this.people;
        this.total = this.bill * 1.10 / this.people;
      }

      if(n === '15%') {
        this.tipAmount = this.bill * 0.15 / this.people;
        this.total = this.bill * 1.15 / this.people;
      }

      if(n === '25%') {
        this.tipAmount = this.bill * 0.25 / this.people;
        this.total = this.bill * 1.25 / this.people;
      }

      if(n === '50%') {
        this.tipAmount= this.bill * 0.50 / this.people;
        this.total = this.bill * 1.50 / this.people;
      }
    },

    initialState(){
      return {
        bill: 0,
        people: 0,
        tipAmount: 0,
        total:0,
        percentages:['5%','10%','15%','25%','50%'],

      }
    },

  /* reset tip */
    reset() {
        this.bill= 0,
        this.people= 0,
        this.tipAmount= 0,
        this.total= 0
      }
    }
  }
  


</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap');

  #app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.template {
  color: black;
}

body {
  font-family: 'Space Mono', monospace;
  background-color: hsl(185, 41%, 84%);
  height: 100vh;
  width: 100vw;
  margin: 0;
  }

.container {
  width: 56%;
  display: flex;
  flex-direction: row;
  flex-flow: row wrap;
  overflow: auto;
  max-height:720px;
  padding: 24px;
  border-radius: 20px;
  background-color: #fff;
  justify-self: center;
  margin: auto;
}

.info {
  flex: 1;
  Width: 60%;
  height: 100%;
  margin-right: 10px;
  padding-left: 10px;
  /*background-color:black; */
  border-radius: 20px;
}

.output {
  flex: 1;
  flex-wrap: wrap;
  background-color:hsl(183, 100%, 15%) ;
  border-radius: 20px;
  padding: Auto 30px;
  margin: 10px Auto;
  margin-right:10px;
}

.reset {
  display: inline-block;
  background-color: hsl(186, 14%, 43%);
  color: hsl(183, 100%, 15%);
  border: none;
  width: 84%;
  height: 44px;
  padding: 20px Auto;
  margin: 6px;
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none;
  font-size: 18px;
  font-weight: 700;
  font-family: inherit;
  margin-top: 70px;
  margin-left: 30px;
}

  .reset:focus {
    background: hsl(172, 67%, 45%);
  }

  p {
    font-size: 13px;
    margin: 0px;
    font-weight: 700;
    color: hsl(186, 14%, 43%);
  }

</style>
