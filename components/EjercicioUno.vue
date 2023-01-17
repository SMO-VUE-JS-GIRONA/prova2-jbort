<template>
  <div>
    <div>
    <h1>Ordenar A-Z</h1>
    <p v-for="(orden, i) in ordenAZ" :key="'orden' + i">
      {{ orden.nom }} - {{ orden.edat }}
    </p>
    </div>
    <hr>
   <!--  <div>
      <h1>Ordenar Z-A</h1>
      <p v-for="(desorden, i) in ordenZA" :key="'desorden' + i">
      {{ desorden.nom }} - {{ desorden.edat }}
    </p>
    </div> -->
  </div>
</template>

<script>
export default {
  data() {
    return{
      ordenAZ : null,
      ordenZA : null,
    }
  },
  props: [
    'personas'
  ],
  mounted() {
    const sortArray= (a, b) => {
      if (a.nom < b.nom) { return -1; }
      if (a.nom > b.nom) { return 1; }
      return 0;
    };
    /* const sortReves= (a, b) => {
      if (a.nom > b.nom) { return -1; }
      if (a.nom < b.nom) { return 1; }
      return 0;
    }; */
     this.ordenAZ = this.personas.sort(sortArray);
     /* this.ordenZA = this.personas.sort(sortReves); */
  }
}
</script>

<style lang="scss" scoped>

</style>