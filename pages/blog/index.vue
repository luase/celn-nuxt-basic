<template>
  <div class="container mt-3">
    <h1>blog</h1>
    <h2>lista de entradas</h2>
    <div v-for="(item, index) in articulos" :key="index" class="card mt-3">
      <div class="card-body">
        <nuxt-link :to="`blog/${item.id}`">
          <h1>{{ item.title }}</h1>
        </nuxt-link>
        <p>{{ item.body }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      articulos: []
    }
  },
  head: {
    title: 'blog'
  },
  async created () {
    try {
      const res = await axios.get('https://jsonplaceholder.typicode.com/posts')
      this.articulos = res.data
    } catch (e) {
      // eslint-disable-next-line no-console
      console.log(e)
    }
  }
}
</script>

<style scoped>

</style>
