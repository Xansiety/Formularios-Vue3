<template>
  <form @submit.prevent="procesarFormulario">

    <input type="text" 
          class="form-control my-2" 
          placeholder="Ingrese su nombre"
          v-model.trim="formulario.nombre">


    <!-- checkbox -->
    <div class="my-2">
      <div class="form-check form-check-inline">
        <input 
          type="checkbox"
          class="form-check-input"
          id="check-1"
          v-model="formulario.categoria"
          value="Javascript"
        >
        <label 
          for="check-1"
          class="form-check-label"
        >Javascript</label>
      </div>
      <div class="form-check form-check-inline">
        <input 
          type="checkbox"
          class="form-check-input"
          id="check-2"
          v-model="formulario.categoria"
          value="NodeJS"
        >
        <label 
          for="check-2"
          class="form-check-label"
        >NodeJS</label>
      </div>
    </div>

    
    <!-- radio -->
    <div class="my-2">
      <div class="form-check form-check-inline">
        <input 
          class="form-check-input" 
          type="radio" 
          id="inlineRadio1" 
          value="urgente"
          v-model="formulario.estado"
        >
        <label class="form-check-label" for="inlineRadio1">
          Urgente
        </label>
      </div>

      <div class="form-check form-check-inline">
        <input 
          class="form-check-input" 
          type="radio" 
          id="inlineRadio2" 
          value="relax"
          v-model="formulario.estado"
        >
        <label class="form-check-label" for="inlineRadio2">
          Relax
        </label>
      </div>
    </div>
 
    <div class="my-2">
      <input 
        type="number"
        class="form-control"
        placeholder="numero"
        v-model.number="formulario.numero"
      >
    </div>
 

      <button class="btn btn-dark mt-2 btn-block" type="submit" :disabled="bloquear">Procesar</button>
    </form>

  <p>
    {{formulario}}
  </p>
</template>

<script>
// @ is an alias to /src 
export default {
  name: 'HomeView',
  components: { },
  data() {
    return {
      formulario: {
        nombre: '',
        categoria: [],
        estado: '',
        numero: 0
      }
    }
  },
  computed: {
  bloquear(){
    return this.formulario.nombre.trim() === '' ? true : false
    }
  },
  methods: {
  procesarFormulario(){
    if(this.formulario.nombre.trim() === ''){
      console.log('nombre Vacío')
      return
    }
    console.log(this.formulario)
     this.formulario = {nombre: '', categoria: [], estado: '', numero: 0}
  }
}
}
</script>
