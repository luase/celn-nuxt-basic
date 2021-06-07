<template>
  <div class="container mt-3">
    <div class="card-body">
      <h1>{{ articulo.title }}</h1>
      <p>{{ articulo.body }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      articulo: ''
    }
  },
  async created () {
    try {
      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
      this.articulo = res.data
    } catch (e) {
      // eslint-disable-next-line no-console
      console.log(e)
    }
  }
}
</script>

<style scoped>

</style>
