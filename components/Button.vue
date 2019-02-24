<template>
  <bButton
    :variant="bsVariant"
    :class="textColorClass"
    :size="bsSize"
    class="button"><slot/></bButton>
</template>

<script>
import bButton from 'bootstrap-vue/src/components/button/button'

export default {
  name: 'Button',
  components: {
    bButton
  },
  props: {
    type: {
      type: String,
      validator: (val) => ['default', 'primary', 'success', 'warning', 'danger'].includes(val),
      default: 'default'
    },
    size: {
      type: String,
      validator: (val) => ['default', 'small', 'large'].includes(val),
      default: 'default'
    }
  },
  computed: {
    bsVariant: function () {
      if (this.type === 'primary') return this.type
      else if (this.type === 'default') return 'outline-primary'
      else return 'outline-' + this.type
    },
    textColorClass: function () {
      if (this.type === 'primary') return ''
      else return 'color-body'
    },
    bsSize: function () {
      return { 'default': '', 'small': 'sm', 'large': 'lg' }[this.size]
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";
@import "~bootstrap/scss/buttons";

.button {
  text-transform: uppercase;
  font-size: $font-size-sm;
}

.btn-lg {
  @include button-size($btn-padding-y-lg, $btn-padding-x-lg, $font-size-sm, $btn-line-height-lg, $btn-border-radius-lg);
}

.btn-sm {
  @include button-size($btn-padding-y-sm, $btn-padding-x-sm, $font-size-sm, $btn-line-height-sm, $btn-border-radius-sm);
}

.color-body {
  color: $body-color;
}
</style>
