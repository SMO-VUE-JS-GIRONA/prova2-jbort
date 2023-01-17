<template>
  <div>
    <EjercicioUno
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioUno>
    <hr>
    <br>
    <EjercicioDos
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioDos>
    <hr>
    <br>
    <EjercicioTres
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioTres>
    <hr>
    <br>
    <EjercicioCuatro
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioCuatro>
    <hr>
    <br><EjercicioCinco
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioCinco>
    <hr>
    <br><EjercicioSeis
    v-if="datosArray"
    :personas="datosArray.persones"
    >
    </EjercicioSeis>
  </div>
</template>

<script>
import datosArray from '@/data/personas';

export default {
    mounted() {
        this.datosArray = datosArray;
    },
    data() {
        return {
            datosArray: null,
        };
    },
}
</script>

<style lang="scss" scoped>

</style>