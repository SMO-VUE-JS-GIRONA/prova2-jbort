<template>
  <div>
    <h1>Eliminar nombre</h1>
    <br>
    <p>Angelica, David, Eva, Jordi, Mar, Pep</p>
    <v-text-field v-model="buscar" placeholder="Elimina unos de estos nombres del array" outlined></v-text-field>
    <v-btn @click="eliminar()"> Eliminar</v-btn>
    <br>
    <p style="margin-top:20px">{{ personas }}</p>
  </div>
</template>

<script>
export default {
  props: [
    'personas'
  ],
  data() {
    return {
      buscar: '',
    }
  },
  methods: {
    eliminar() {
      let borrar = -1;
      this.personas.forEach((persona, i) => {
        if (persona.nom.toLowerCase() == this.buscar.toLowerCase()) {
          borrar = i;
        }
      })
      if (borrar != -1) {
        this.personas.splice(borrar, 1);
      }
    }
  }
}
</script>