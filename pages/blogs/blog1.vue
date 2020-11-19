<template>
  <div v-html="blog1"></div>
</template>

<script>
  import blog1 from '../../product/ball1.md'

  export default {
    computed: {
      blog1() {
        return blog1
      }
    }
  }
</script>