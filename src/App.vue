<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div class="content flex">
      <Puzzle></Puzzle>
      <PuzzleSettings></PuzzleSettings>
    </div>
  </div>
</template>

<script>
import Puzzle from './components/Puzzle.vue'
import PuzzleSettings from './components/PuzzleSettings.vue'

export default {
  name: 'App',
  components: {
    Puzzle,
    PuzzleSettings
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Roboto', sans-serif;
  * {
    transition: .25s;
    outline: none;
    box-sizing: border-box;
  }
}
.content {
  padding: 20px;
  @media only screen and (max-width: 992px){
    & {
      padding: 20px 0;
    }
  }
}
.flex {
  display: flex;
}
.pointer {
  cursor: pointer;
}
input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
input[type="number"] {
  -moz-appearance: textfield;
}
input[type="number"]:hover,
input[type="number"]:focus {
  -moz-appearance: number-input;
}
input[type=number]::-webkit-inner-spin-button,
input[type=number]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
