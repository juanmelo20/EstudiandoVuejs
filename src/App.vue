<script setup>
const msg = 'Vue 3 eventos'
const onclick = () =>{
      alert('me has pinchado')
}    
</script>

<template>
 <h1>{{ msg }}</h1>
 <button @click="onclick">Dar click</button>
</template>

<style scoped>

</style>
