<!-- el SFC (Single File Components) permite tener en un mismo "archivo" la lógica(Script), la estructura (Template) y el estilo (Style)-->
<!-- el unico obligatorio es el template -->
<script setup>
  // const name = 'Vue dinámico'
  // const styleColor = "color:blue"
  // const arrayColores = ["blue","red","Argentina"]
  // const estado = true
  // const cantidad = 100
  // const servicios = ["Transferencias","Depositos","Giros"];
  // const arrayFrutas = [
  //   {
  //     name:"Manzana",
  //     price:"$1.00",
  //     description: "Una Manzana",
  //     stock: 0,
  //   },
  //     {
  //     name:"Pera",
  //     price:"$2.00",
  //     description: "Una Pera",
  //     stock: 10,
  //   },
  //     {
  //     name:"Naranja",
  //     price:"$3.00",
  //     description: "Una Naranja",
  //     stock: 20,
  //   },
  //     {
  //     name:"Banana",
  //     price:"$4.00",
  //     description: "Una Banana",
  //     stock: 30,
  //   },
  // ]

  // const objetoFruta =  {
  //     name:"Manzana",
  //     price:"$1.00",
  //     description: "Una Manzana",
  //     id: 1
  //   }

  //metodo - methods
  const handleClick = (message) => {
    console.log(message)
  }
</script>

<template>
 <!-- <h1>Hola {{name.toUpperCase()}} </h1>--> <!--las llaves dobles permitern escribir codigo JavaScript en el HTML -->
  <h1>Hola </h1>
  <!-- <h2 v-bind:style="styleColor"> Soy Azul</h2> <h2 :style="styleColor"> Soy Azul</h2> PUEDE ESCRIBIRSE ASI TAMBIEN, SIN V-BIND  -->
<!-- <br>
<h2>{{arrayColores}}</h2>

       <h2 v-if="estado">Cuenta Activada</h2>
       <h2 v-else>Cuenta Desactivada</h2>

      

        <h2 v-if="cantidad > 500">Cantidad: {{cantidad }}</h2>
        <h2 v-else-if="cantidad <= 500 && cantidad > 0">
            Cantidad: 
            <span style="color:red">{{cantidad }}</span>
        </h2>
        <h2 v-else>Sin cantidad</h2> -->

<!-- Siempre que trabajemos con v-for, Vue nos pedirá que estos elementos tengan una llave única, podemos agregar por ahora un index -->
            <!-- <ul>
            
            <li v-for="(item, index) in servicios" :key="index">{{index+1}} - {{item}}</li>
        </ul> 

        <ul>
          <li  v-for="(fruta) in arrayFrutas" :key="fruta.name"> {{fruta.description}} - {{fruta.price}} - {{fruta.name}}
            
          </li>
        </ul> -->

      <!-- {{objetoFruta}}
        <ul>
          <li
          v-for="(value, propiedad,index) in objetoFruta" :key="index">
            {{index}} -{{propiedad}}: {{value}}
          </li>
        </ul> -->

         <!-- V-FOR+V-IF+TEMPLATE-->
        <!-- <ul>
<template v-for="item in arrayFrutas" :key="item.name">
   <li v-if="item.stock >0"> {{item.name}} - {{item.price}} </li>
</template>         
        </ul> -->

<!-- <button v-on:click="handleClick('Texto 1')">Activame 1</button>
<button @click="handleClick('Texto 2')">Activame 2</button> -->

<!--EVENTOS DE LOS BOTONES DEL MOUSE. RIGHT BOTON DERECHO, PREVENT PARA QUE NO SALGA EL POP-UP DEL CLICK DERECHO -->
<button v-on:click.right.prevent="handleClick('Texto Right')">Activame Right</button> 
<button @click="handleClick('Texto Left')">Activame Left</button>
<button v-on:click.middle="handleClick('Texto Middle')">Activame Middle</button>

</template>

<style>
  h1{
    color: red;
  }
</style>