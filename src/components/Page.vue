<template>
    <div :class="[{ left: side === 'left', right: side === 'right'}, 'page']">
        <h3 class="spell">
        {{spell.spell}}
        </h3>
        <p class="type">({{spell.type}})</p>
        <p>{{spell.effect}}</p>
        <button @click="$emit('changePage', side === 'right' ? 'next' : 'previous')" :class="{ buttonleft: side === 'left', buttonright: side === 'right'}"></button>
    </div>
</template>
<script>
export default {
    props:[
        'side',
        'spell',
    ],  
}
</script>
<style>
.page {
  font-family: 'Princess Sofia', cursive;
  width: 50%;
  height: 100%;
  padding: 10px;
  position: relative;
}
.left {
  border-radius: 2px 10px 10px 2px;
  border-right: 0.3px solid black;
  background-image: linear-gradient(to right, #ffffff, #ffffff, #ffffff, #ffffff, #ffffff, #fbfbfb, #f6f6f6, #f2f2f2, #e8e8e8, #dedede, #d4d4d4, #cacaca);
}
.right {
  border-radius: 10px 2px 2px 10px;
  border-left: 0.3px solid black;
  background-image: linear-gradient(to left, #ffffff, #ffffff, #ffffff, #ffffff, #ffffff, #fbfbfb, #f6f6f6, #f2f2f2, #e8e8e8, #dedede, #d4d4d4, #cacaca);
}
.spell {
  font-size: 1.5rem;
  padding: 5px;
  margin: 2px 5px;
}
p {
  font-family: 'Raleway', sans-serif;
  font-size: 0.8rem
}
.type {
  font-family: 'Butterfly Kids', cursive;
}
.buttonleft {
  border: solid black;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 3px;
  transform: rotate(135deg);
  -webkit-transform: rotate(135deg);
  position: absolute;
  top: 50%;
  left: 10%;
}
.buttonleft:hover {
  border-width: 0 4px 4px 0;
  cursor: pointer;
}

.buttonleft:focus{
  outline: none;
}
.buttonright {
  border: solid black;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 3px;
  transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
  position: absolute;
  top: 50%;
  right: 10%;
}
.buttonright:hover {
  border-width: 0 4px 4px 0;
  cursor: pointer;
}
.buttonright:focus{
  outline: none;
}
</style>