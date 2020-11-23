<template>
  <div v-html="blog3"></div>
</template>

<script>
  import blog3 from '../../content/product/ball3.md'

  export default {
    computed: {
      blog3() {
        return blog3
      }
    }
  }
</script>