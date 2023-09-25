<script setup>
  import Formulario from './components/Formulario.vue'
  import Clima from  './components/Clima.vue'
  import Spinner from './components/Spinner.vue'
  import Alerta from './components/Alerta.vue'
  import useClima from './composables/useClima'
  const { obtenerClima, clima, mostrarClima, cargando, error} = useClima()
</script>

<template>
  <h1 class="titulo"> Buscador de Clima </h1>

  <div class="contenedor buscador-clima">
    <Formulario @obtener-clima="obtenerClima"/>
    
    <Spinner v-if="cargando"/>
    
    <Alerta v-if="error"> {{ error }} </Alerta>
    
    <Clima v-if="mostrarClima" :clima="clima"/>
  </div>
</template>
