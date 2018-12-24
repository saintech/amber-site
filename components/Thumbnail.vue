<template>
  <img
    :src="url"
    :alt="description"
    class="image">
</template>

<script>
import bLink from 'bootstrap-vue/src/components/link/link'

export default {
  name: 'Thumbnail',
  components: {
    bLink
  },
  props: {
    url: {
      type: String,
      default: 'data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs='
    },
    description: {
      type: String,
      required: true
    },
    to: {
      type: [String, Object],
      default: ''
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";

.image {
  object-fit: cover;
  height: 17rem;
  width: 100%;
  margin-bottom: $grid-gutter-width;
  cursor: pointer;
}
</style>
