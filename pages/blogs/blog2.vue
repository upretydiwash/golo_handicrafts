<template>
  <div v-html="blog2"></div>
</template>

<script>
  import blog2 from '../../blog/blog2.md'

  export default {
    computed: {
      blog2() {
        return blog2
      }
    }
  }
</script>