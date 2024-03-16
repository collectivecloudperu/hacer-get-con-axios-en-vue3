<template>  

  <!-- Contenedor para la imagen -->
  <img v-bind:src="img" class="img-fluid">

</template>
<!-- test -->
<script setup>
  
  // Importamos axios 
  import axios from 'axios';

  // Importamos 'ref' de Vue 3
  import {ref} from "vue"
  
  // Hacemos la variable 'img' reactiva 
  const img = ref(null)
  
  // Hacemos una petición a la Dog API 
  axios.get('https://dog.ceo/api/breeds/image/random')
    .then(function (response) {

      // Mostramos los datos obtenidos en la consola 
      console.log(response);

      // Accedemos a una imagen aleatoria de un perro 
      img.value = response.data.message;
      
      // Mostramos la imagen aleatoria obtenida de un perro en la consola 
      console.log(img);
  
    })
    .catch(function (error) {
  
      // Si hubo algun error mostramos algo 
      console.log(error);
  
    })
    .finally(function () {
  
      // Se ejecuto sin problemas 
      
    });
 
</script>

<style>
  /* */
</style>
