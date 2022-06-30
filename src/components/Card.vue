<template>
  
  <div class="card mb-3">
    <div class="card-body">
        <h2 class="text-center">{{pais.name}}</h2>
        <p class="text-center">
            <img :src="pais.flag" :alt="`bandera de ${pais.name.common}`" class="img-fluid w-25 border border-2">
        </p>
        <p class="card-text">
            <span class="badge bg-dark d-block mb-1">Capital: {{pais.capital}}</span>
            <span class="badge bg-dark d-block mb-1">Región: {{pais.region}}</span>
            <span class="badge bg-success p-2 d-block mb-1">Poblacion: {{nroFormat(pais.population)}}</span>
        </p>
    </div>
  </div>

</template>

<script>
export default {

    props: ['pais'],

    setup(){

        const nroFormat = (num) => {
            return new Intl.NumberFormat("de-DE").format(num);
        }


        return {nroFormat}
    }

}
</script>