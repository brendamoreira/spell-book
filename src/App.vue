<template>
  <div id="app">
    <h1 class="title">SpellBook</h1>
    <div class="book">
      <div class="pageleft">
      </div>
      <div class="pageright">
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  components: {
    
  },
  data() {

  },
  methods: {
    spellList(){
      axios
      .get()
      .then()
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Butterfly+Kids&family=Montez&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Princess+Sofia&family=Raleway:wght@200&display=swap');

  /* font-family: 'Montez', cursive;
  font-family: 'Butterfly Kids', cursive;
  font-family: 'Princess Sofia', cursive;
  font-family: 'Raleway', sans-serif;   */

body{
  margin: 0;
}
#app {
  width: 100vw;
  height: 100vh;
  background-color: rgb(95, 0, 136);
}

.title{
  font-family: 'Montez', cursive;
  font-size: 3rem;
  text-shadow: 2px 2px 8px rgb(57, 57, 57);
  color: rgb(249, 240, 255);
  margin: 0;
  text-align: center;
}
.book {
  margin: 20px auto;
  width: 600px;
  height: 400px;
  border-radius: 8px;
  border: 20px solid black;
  background-color: black;
  box-sizing: border-box;
  display: flex;
}
.pageleft {
  background-color: #f2eecb;
  width: 50%;
  height: 100%;
  border-radius: 2px 10px 10px 2px;
  border-right: 0.3px solid black;
  background-image: linear-gradient(to left, #c1c1c1, #cccccc, #d8d8d8, #e3e3e3, #efefef, #f4f4f4, #fafafa, #ffffff, #ffffff, #ffffff, #ffffff, #ffffff);
}
.pageright {
  width: 50%;
  height: 100%;
  border-radius: 10px 2px 2px 10px;
  border-left: 0.3px solid black;
  background-image: linear-gradient(to right, #c1c1c1, #cccccc, #d8d8d8, #e3e3e3, #efefef, #f4f4f4, #fafafa, #ffffff, #ffffff, #ffffff, #ffffff, #ffffff);}
</style>
