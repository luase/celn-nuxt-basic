<template>
  <div class="container mt-3">
    <h1>blog</h1>
    <h2>lista de entradas</h2>
    <div class="row">
      <div v-for="(item, index) in articulos" :key="index" class="col-md-3">
        <h2>
          <nuxt-link :to="`/blog/${ item.id }`">
            {{ item.titulo }}
          </nuxt-link>
        </h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      articulos: [
        { id: 1, titulo: 'articulo 1' },
        { id: 2, titulo: 'articulo 2' },
        { id: 3, titulo: 'articulo 3' },
        { id: 4, titulo: 'articulo 4' },
        { id: 5, titulo: 'articulo 5' }
      ]
    }
  }
}
</script>

<style scoped>

</style>
