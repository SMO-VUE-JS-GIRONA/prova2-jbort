<template>
  <div>
    <h1>Buscar por edad</h1>
    <br>
    <v-text-field v-model="buscar" placeholder="Pon los años de una persona" outlined></v-text-field>
    <v-btn @click="busqueda"> Buscar</v-btn>
    <br>
    <p style="margin-top:20px">{{ resultado }}</p>
  </div>
</template>

<script>
  export default {
    props: [
      'personas'
    ],
    data() {
      return {
        buscar:'',
        filtro:null,
        resultado: '',

      }
    },
    methods: {
      busqueda() {
          this.filtro = this.personas.filter(persona=>persona.edat.toLowerCase().includes(this.buscar.toLowerCase()));
          if(this.filtro.length <= 0){
            this.resultado = 'La edad NO se encuentra en nuestra base de datos';
            return this.resultado;
          }else {
            this.resultado = 'La edad SI se encuentra en nuestra base de datos';
            return this.resultado;
          }
        
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>