<template>
  <div id="app">
    <h1 class="title">Roll the dice!</h1>
    <div class="btn" @click="roll">ROLL</div>
    <div class="dice-area">
      <img v-if="number > 0" :src="getSrc()" alt="test">
    </div>

  </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      number: 0,
    }
  },

  methods: {
    roll() {
      this.number = Math.floor(Math.random() * 6) + 1;
    },

    getSrc() {
      return require('./assets/img/Dice-'+ this.number +'.png');
    }

    
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  background: #123;
}

.title {
  padding: 10px;
  text-align: center;
  color: #ffffff;
  border-bottom: 2px solid crimson;
  font-size: 50px;
}

.btn {
  width: 250px;
  padding: 20px;
  margin: 50px auto;
  background: crimson;
  color: #fff;
  border: 1px solid #fff;
  border-radius: 10px;
  text-align: center;
  font-size: 20px;
  cursor: pointer;
}

.dice-area {
  padding: 20px;
  background: #fff;
}

img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

</style>
