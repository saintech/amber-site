<template>
  <article :class="{'lead-p': leadP}">
    <slot/>
  </article>
</template>

<script>

export default {
  name: 'Article',
  props: {
    // make first paragraph large
    leadP: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";
@import "~bootstrap/scss/type";

h1 {
  color: $primary;
}

article {
  &.lead-p > p:first-of-type {
    font-size: $lead-font-size;
    font-weight: $lead-font-weight;
  }
}
</style>
