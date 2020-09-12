<template>
  <div id="dice-roller">
    <div id="input">
      <h2>Input</h2>
      <p>Roll d2 <button v-on:click="roll(2)">Click Me!</button></p>
      <p>Roll d4 <button v-on:click="roll(4)">Click Me!</button></p>
      <p>Roll d6 <button v-on:click="roll(6)">Click Me!</button></p>
      <p>Roll d8 <button v-on:click="roll(8)">Click Me!</button></p>
      <p>Roll d10 <button v-on:click="roll(10)">Click Me!</button></p>
      <p>Roll d12 <button v-on:click="roll(12)">Click Me!</button></p>
      <p>Roll d20 <button v-on:click="roll(20)">Click Me!</button></p>
      <p>Roll d100 <button v-on:click="roll(100)">Click Me!</button></p>
    </div>
    <div id="output">
      <h2>Output</h2>
      <p v-for = "(item, index) in response" :key="index">{{item}}</p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function() {
    return {
      response: []
    }
  },
  methods: {
    roll: function(sides) {
      let result = (Math.floor(1 + (Math.random() * sides)));
      this.response.push("You rolled a: " + result)
    }
  }

}
</script>

<style>
  body {
    background: black;
  }
  #dice-roller {
    color: cyan;
  }
  #input {
    color: cornflowerblue;
  }
  #output {
    color:hotpink;
  }
</style>
