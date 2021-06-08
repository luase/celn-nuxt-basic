<template>
  <div class="container mt-3">
    <div class="card-body">
      <h1>{{ articulo.title }}</h1>
      <p class="small">
        {{ articulo.nombreAutor }}
      </p>
      <p>{{ articulo.body }}</p>
      <nuxt-link to="/blog" class="btn btn-primary">
        volver
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ params }) {
    try {
      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
      const articulo = res.data
      const resAutor = await axios.get(`https://jsonplaceholder.typicode.com/users/${res.data.userId}`)
      articulo.nombreAutor = resAutor.data.name
      return { articulo }
    } catch (e) {
      // eslint-disable-next-line no-console
      console.log(e)
      return { e }
    }
  }
}
</script>

<style scoped>

</style>
