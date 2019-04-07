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
@import "../assets/bootstrap/type";

h1 {
  color: $primary;
}

@include media-breakpoint-up(lg) {
  h1 {
    font-size: $font-size-base * 5;
  }
}

h1, h2, h3, h4, h5, h6 {
  text-transform: uppercase;
}

article {
  &.lead-p > p:first-of-type {
    font-size: $lead-font-size;
    font-weight: $lead-font-weight;
  }
}
</style>
