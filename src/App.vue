<!-- el SFC (Single File Components) permite tener en un mismo "archivo" la lógica(Script), la estructura (Template) y el estilo (Style)-->
<!-- el unico obligatorio es el template -->
<script setup>
import {ref, computed} from 'vue'

   const name = 'Vue dinámico';

   const counter = ref(0); // este ref indica que la variable es reactiva, y que por lo tanto podrá cambiar su valor. El cero es el valor en el que inicializa, podria ser false x ej u otra cosa.
   const cantidad = 0
   let arrayNumerosFavoritos = ref([])

   const increment = () => {
  //   console.log('aumentar contador');
     counter.value ++ //aqui en el SCRIPT, hay que usar value para poder acceder a su valor (el 0 que aumentara su valor), ya que vue devuelve un objeto. Debajo en template NO.
//     console.log(counter)
   }

   const decrement = () => counter.value --  // otras maneras de hacer una funcion, escrita mas abreviada
   const reset = () => (counter.value = 0)
  
   const add = () => {
  arrayNumerosFavoritos.value.push(counter.value) // se usa PUSH para "empujar" valores, y no ADD
}


   //estas clases computadas siempre tienen que devolver algo, es decir un return (video 34, seccion 3)
  const classCounter = computed(() => {
      if (counter.value === 0)
      {
        return 'zero'
      }

      if (counter.value > 0)
      {
        return 'positive'
      }

      if (counter.value < 0)
      {
        return 'negative'
      }
  })

  const bloquearBtnAdd = computed(() => {

      const numSearch = arrayNumerosFavoritos.value.find(num => num === counter.value)
console.log(numSearch)

if(numSearch === 0) return true

return numSearch ? true : false 
  })




</script>

<template>
<div class="container text-center">
 <!--<h2 :class="counter > 0 ? 'positive' : 'negative' ">{{counter}}</h2> >>>>> clase dinamica en la que cambia de color segun el valor de counter-->
 <h2 :class="classCounter">{{counter}}</h2> 
 <div class="btn-group"> 
<button @click="increment" class="btn btn-success">Aumentar</button>
<button @click="decrement" class="btn btn-danger">Disminuir</button>
<button @click="reset" class="btn btn-secondary">Resetear</button>
<button @click="add" :disabled="bloquearBtnAdd" class="btn btn-primary">Agregar</button>
</div>
<!-- <br/>
{{arrayNumerosFavoritos}} -->
<ul class="list-group mt-4">  
    <li class="list-group-item" v-for= "(num,index) in arrayNumerosFavoritos" :key="index"> 
      {{num}}
    </li>
</ul>
</div>
</template>

<style>
  h1{
    color: red;
  }

  .positive {
    color: green;
  }

  .negative {
    color:red;
  }

  .zero {
    color: peru
  }
</style>