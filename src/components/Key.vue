<template>
    <div>
        <form @submit.prevent="$emit('submit', apiKey)">
            <input type="text" v-model="apiKey" placeholder="Type your key">
            <button type="submit">Enter</button>
        </form>
    </div>
</template>
<script>
export default {
    name:'Key',
    data() {
        return{
            apiKey: '',
        }
    },
}
</script>
<style scoped>
input{
    font-family: 'Raleway', sans-serif;
    font-size: 0.6rem;
    width: 200px;
    height: 16px;
    margin: auto;
    border: none;
    border-radius: 2px;
    opacity: 80%;
}
button{
    margin: 2px;
    border: none;
    border-radius: 2px;
    height: 16px;
    opacity: 85%;
}
button:hover{
    opacity: 100%;
}
</style>