<template>
    <div :class="[{open: spells.length, closed: !spells.length}, 'book']">
        <h2>Wizarding World's<br><br> Spellbook
        </h2>
      <page @changePage="changePage" v-for="(spell, idx) in page" :key="spell.id" :side="idx % 2 === 0 ? 'left' : 'right'" :spell="spell">
      </page>
    </div>
    
</template>
<script>
import Page from './Page'
export default {
  name: 'Book',
  components: {
    Page,
  },
  props:[
    'spells'
  ],
  data(){
    return{
        pageNumber: 1,
      }
  },
  methods:{
      changePage(prevNext){
          if(prevNext == 'next'){
            if(this.pageNumber+1 != this.spells.length){
                this.pageNumber = this.pageNumber+1;
            }
          } else{
              if(this.pageNumber-1 != 0){
                this.pageNumber = this.pageNumber-1;
              }
          }
      }
  },
  computed:{
    page() {
        let index = (this.pageNumber-1)*2
        return this.spells.slice(index, index+2)
    }
  }
}
</script>
<style>
.book {
  margin: 20px auto;
  border-radius: 8px;
  height: 400px;
  border: 15px solid black;
  box-sizing: border-box;
  display: flex;
}
h2{
  font-family: 'Butterfly Kids', cursive;
  font-size: 2.5rem;
  text-align: center;
  margin: auto;
  color: rgb(235, 235, 235);
  text-shadow: 2px 3px 4px rgb(29, 29, 29);
}
.open{
  width: 600px;
  background-color: black;
}
.open h2 {
    display: none;
}
.closed{
    width: 300px;
    background-image: radial-gradient(circle, #4c0059, #4e005e, #510062, #530067, #55006c, #540060, #520055, #4f004b, #410433, #300820, #1e0612, #000000);}
</style>