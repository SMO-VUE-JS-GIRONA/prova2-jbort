<template>
  <div>
    <h1>Buscar nombre</h1>
    <br>
    <v-text-field v-model="buscar" placeholder="Pon un nombre de persona" outlined></v-text-field>
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
          this.filtro = this.personas.filter(persona=>persona.nom.toLowerCase().includes(this.buscar.toLowerCase()));
          if(this.filtro.length <= 0){
            this.resultado = 'El nombre NO se encuentra en nuestra base de datos';
            return this.resultado;
          }else {
            this.resultado = 'El nombre SI se encuentra en nuestra base de datos';
            return this.resultado;
          }
           /* this.personas.forEach((persona) => {
             if(persona.nom.toLowerCase() == this.buscar.toLowerCase()) {
               this.filtro = 'El nombre se encuentra en nuestra base de datos';
               return this.filtro;
             }else{
               this.filtro = 'El nombre no se encuentra';
               return this.filtro;
             }
          }) */
        
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>