<template>
  <bCard
    :style="{backgroundImage: 'url(' + icon + ')'}"
    class="product">
    <h4 class="title"><bLink>Product <span class="name">«Test»</span></bLink></h4>
    <slot/>
    <Button
      slot="footer"
      class="about"
      size="small">Узнать цену</Button>
  </bCard>
</template>

<script>
import bCard from 'bootstrap-vue/src/components/card/card'
import bLink from 'bootstrap-vue/src/components/link/link'
import Button from './Button'

export default {
  name: 'Product',
  components: {
    Button,
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
@import "../assets/bootstrap/type";
@import "../assets/bootstrap/card";

.product {
  background-repeat: no-repeat;
  background-position: left 10.5rem bottom 1.5rem;
  margin-bottom: $grid-gutter-width;
  height: calc(100% - #{$grid-gutter-width});
}

.title {
  font-size: 1.25rem;
}

.name {
  font-weight: $font-weight-bold;
}

.card-body {
  font-size: $small-font-size;
  font-weight: $font-weight-normal;

  > p {
    width: 8.75rem;

    &:first-of-type {
      font-size: $font-size-base;
    }

    &:last-child {
      margin-bottom: 0;
    }
  }
}

.about {
  width: 8.75rem;
}

.card-footer {
  padding-top: 0;
}
</style>
