<template>
  <bCard
    :style="{backgroundImage: 'url(' + icon + ')'}"
    class="feature">
    <h4 class="title">У нас</h4>
    <strong class="card-text">{{ text }}</strong>
    <bLink
      slot="footer"
      :to="to">Подробнее</bLink>
  </bCard>
</template>

<script>
import bCard from 'bootstrap-vue/src/components/card/card'
import bLink from 'bootstrap-vue/src/components/link/link'

export default {
  name: 'Feature',
  components: {
    bCard,
    bLink
  },
  props: {
    text: {
      type: String,
      default: '[empty]'
    },
    icon: {
      type: String,
      default: ''
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

.feature {
  padding: 0.25rem 0.375rem 0.25rem 0.375rem;
  background-repeat: no-repeat;
  background-position: right 1.5rem bottom 1.5rem;
  margin-bottom: $grid-gutter-width;
}

.title {
  font-size: 1.25rem;
  color: $text-muted;
  text-transform: uppercase;
}

.card-body {
  padding-right: 0.9rem;
}

.card-text {
  font-family: $headings-font-family;
  font-size: 3.5rem;
  font-weight: $font-weight-normal;
  line-height: $line-height-base / 1.5;
  color: $primary;
  text-transform: uppercase;
  white-space: pre-line;
  margin-right: 5.75rem;
}
</style>
