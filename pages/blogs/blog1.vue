<template>
  <div v-html="blog1"></div>
</template>

<script>
  import blog1 from '../../content/product/ball1.md'

  export default {
    computed: {
      blog1() {
        return blog1
      }
    }
  }
</script>