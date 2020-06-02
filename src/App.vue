<template>
  <div id="app">
    <h1 class="title">SpellBook</h1>
    <key @submit="spellList"/>
    <book :spells="spells"/>
  </div>
</template>

<script>
import axios from 'axios'
import Book from './components/Book.vue'
import Key from './components/Key.vue'

export default {
  name: 'App',
  components: {
    Book,
    Key
  },
  data(){
    return{
      spells: [],
    }
  },
  methods: {
    spellList(key){
      axios
      .get(`https://www.potterapi.com/v1/spells?key=${key}`)
      .then(response => {
        this.spells = response.data
      })
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Butterfly+Kids&family=Montez&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Princess+Sofia&family=Raleway:ital,wght@1,200&display=swap');
  /* font-family: 'Montez', cursive;
  font-family: 'Butterfly Kids', cursive;
  font-family: 'Princess Sofia', cursive;
  font-family: 'Raleway', sans-serif;   */

*{
  box-sizing: border-box;
}
body{
  margin: 0;
}
#app {
  width: 100vw;
  height: 100vh;
  /*background-image: linear-gradient(to bottom, #530077, #57037b, #5b077f, #5f0b83, #630f87, #68148c, #6c1990, #711d95, #77239c, #7e29a3, #842faa, #8b35b1);*/
  background-image: linear-gradient(to bottom, #530077, #4d1066, #451955, #3d1e46, #332237);  text-align: center;
}

.title{
  font-family: 'Montez', cursive;
  font-size: 3rem;
  text-shadow: 2px 2px 5px rgb(29, 29, 29);
  color: rgb(249, 240, 255);
  margin: 0;
  text-align: center;
}
</style>
