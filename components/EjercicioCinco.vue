<template>
  <div>
    <h1>Ordenar por tamaño</h1>
    <br>
  <v-btn @click="tamaño()">Ordenar</v-btn>
  <p style="margin-top:20px">{{ personas }}</p>
  </div>
</template>

<script>
  export default{
      props:[
        'personas'
      ],
      methods:{
          tamaño(){
          this.personas.sort((a, b) => {
          if (a.nom.length < b.nom.length) return -1;
          if (a.nom.length > b.nom.length) return 1;
          return 0;
      });
   }
 }
}
</script>