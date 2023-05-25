<script setup>
const msg = 'Vue 3 eventos'
const onclick = (msg) =>{
      console.log(msg)
}    
</script>

<template>
 <h1>{{ msg }}</h1>
 <button @click.right.prevent="onclick('me has dado click con el boton derecho')">Dar click derecho</button>
 <button @click.left="onclick('me has dado click con el boton izquierdo')">Dar click izquierdo</button>
</template>

<style scoped>

</style>
