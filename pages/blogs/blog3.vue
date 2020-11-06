<template>
  <div v-html="blog3"></div>
</template>

<script>
  import blog3 from '../../blog/blog3.md'

  export default {
    computed: {
      blog3() {
        return blog3
      }
    }
  }
</script>