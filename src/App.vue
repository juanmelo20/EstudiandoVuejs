<script setup>
import { ref , computed } from 'vue';

const contador = ref(0)
const arraysAgregados =ref([])
const incrementar = () => {
      console.log('aumentando contador')
      contador.value++
      console.log(contador.value)
}
const decrementar = () => {
      console.log('disminuyendo contador')
      contador.value--
      console.log(contador.value)
}

const limpiar =()=>{
            contador.value = 0;
      }

// eslint-disable-next-line vue/return-in-computed-property
const classContador = computed(()=>{
      if (contador.value === 0){
            return 'zero'
      }
      if(contador.value > 0){
            return 'positive'
      }
      if(contador.value < 0){
            return 'negative'
      }
})
const desactivarAdd = computed(()=>{
      const numSearch = arraysAgregados.value.find(num => num === contador.value)
     /* if(numSearch===0){
            return true
      }
      return numSearch ? true : false*/
      
      return numSearch || numSearch==0
     
})

const Add=()=>{
      arraysAgregados.value.push(contador.value)   
}
</script>

<template>
      <div class="">
                  <h2 :class="classContador">
                  {{ contador }}
            </h2>
            <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 24 24">
                  <g fill="none">
                        <path d="M12.5 2.75a.75.75 0 0 0-1.5 0V3H5.25A3.25 3.25 0 0 0 2 6.25v9.5A3.25 3.25 0 0 0 5.25 19h2.398l-1.475 1.77a.75.75 0 0 0 1.153.96L9.6 19h3.508c.334-1.156 1.4-2 2.664-2h.277A3.5 3.5 0 1 1 22 14.5V6.25A3.25 3.25 0 0 0 18.75 3H12.5v-.25zm-6.5 5A.75.75 0 0 1 6.75 7h4a.75.75 0 0 1 0 1.5h-4A.75.75 0 0 1 6 7.75zM6.75 10h6.5a.75.75 0 0 1 0 1.5h-6.5a.75.75 0 0 1 0-1.5zm0 3h5.5a.75.75 0 0 1 0 1.5h-5.5a.75.75 0 0 1 0-1.5zM21 14.5a2.5 2.5 0 1 1-5 0a2.5 2.5 0 0 1 5 0zm2 5.375C23 21.431 21.714 23 18.5 23S14 21.437 14 19.875v-.103c0-.98.794-1.772 1.773-1.772h5.454c.98 0 1.773.793 1.773 1.772v.103z"
                              fill="currentColor"></path>
                  </g>
            </svg>
            <br>
            <button @click="decrementar">-</button>
            <button @click="limpiar">Limpiar</button>
            <button @click="incrementar">+</button>
            <br>
            <button @click="Add" :disabled="desactivarAdd" >Add</button>
            <br>
            <h1>
                  {{ arraysAgregados }}
            </h1>
            <ul>
                  <li v-for="(num) in arraysAgregados" :key="num">
                  {{ num }}
                  </li>
            </ul>
           
 
      </div>
      
</template>

<style scoped>
.negative{
      color: red;
}
.positive{
      color: green;
}
.zero{
      color: peru;
}
svg {
      height: 300px;
      width: 300px;
}
button{
      margin-left: 25px;
      padding-left: 0.5cm;
      padding-right: 0.5cm;
      background: rgb(162, 221, 221);
}
h2{
      margin-left: 250px;
      font-size: 50px;
      color: aqua;
}
</style>
