<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">
      pagina no encontrada
    </h1>
    <h1 v-else>
      ha ocurrido un error
    </h1>
    <NuxtLink to="/">
      inicio
    </NuxtLink>
  </div>
</template>

<script>
export default {
  layout: 'blog',
  // eslint-disable-next-line vue/require-prop-types
  props: ['error'] // you can set a custom layout for the error page
}
</script>
