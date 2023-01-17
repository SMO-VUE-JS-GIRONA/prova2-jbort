<template>
  <div>
    <h1>Persona más mayor</h1>
    <p>Resultado en la consola{{ personaMayor }}</p>
  </div>
</template>

<script>
export default {
  props: [
    'personas'
  ],
  computed: {
    personaMayor() {
      let mayor = 0
      this.personas.forEach((persona, i) => {
        if (persona.edat > this.personas[mayor].edat) {
          mayor = i;
        }
      })
      console.log("La persona más mayor es " + this.personas[mayor].nom, this.personas[mayor].edat)
    }
  },
}
</script>

<style lang="scss" scoped>

</style>