<template>
  <bButton
    :variant="bsVariant"
    :class="textColorClass"
    :size="bsSize"
    class="button">
    <svg
      v-if="icon === 'question'"
      focusable="false"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 384 512">
      <path
        fill="currentColor"
        d="M202.021 0C122.202 0 70.503 32.703 29.914 91.026c-7.363 10.58-5.093 25.086 5.178 32.874l43.138 32.709c10.373 7.865 25.132 6.026 33.253-4.148 25.049-31.381 43.63-49.449 82.757-49.449 30.764 0 68.816 19.799 68.816 49.631 0 22.552-18.617 34.134-48.993 51.164-35.423 19.86-82.299 44.576-82.299 106.405V320c0 13.255 10.745 24 24 24h72.471c13.255 0 24-10.745 24-24v-5.773c0-42.86 125.268-44.645 125.268-160.627C377.504 66.256 286.902 0 202.021 0zM192 373.459c-38.196 0-69.271 31.075-69.271 69.271 0 38.195 31.075 69.27 69.271 69.27s69.271-31.075 69.271-69.271-31.075-69.27-69.271-69.27z"/>
    </svg>
    <svg
      v-else-if="icon === 'vk'"
      focusable="false"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 576 512">
      <path
        fill="currentColor"
        d="M545 117.7c3.7-12.5 0-21.7-17.8-21.7h-58.9c-15 0-21.9 7.9-25.6 16.7 0 0-30 73.1-72.4 120.5-13.7 13.7-20 18.1-27.5 18.1-3.7 0-9.4-4.4-9.4-16.9V117.7c0-15-4.2-21.7-16.6-21.7h-92.6c-9.4 0-15 7-15 13.5 0 14.2 21.2 17.5 23.4 57.5v86.8c0 19-3.4 22.5-10.9 22.5-20 0-68.6-73.4-97.4-157.4-5.8-16.3-11.5-22.9-26.6-22.9H38.8c-16.8 0-20.2 7.9-20.2 16.7 0 15.6 20 93.1 93.1 195.5C160.4 378.1 229 416 291.4 416c37.5 0 42.1-8.4 42.1-22.9 0-66.8-3.4-73.1 15.4-73.1 8.7 0 23.7 4.4 58.7 38.1 40 40 46.6 57.9 69 57.9h58.9c16.8 0 25.3-8.4 20.4-25-11.2-34.9-86.9-106.7-90.3-111.5-8.7-11.2-6.2-16.2 0-26.2.1-.1 72-101.3 79.4-135.6z"/>
    </svg>
    <svg
      v-else-if="icon === 'fb'"
      focusable="false"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 264 512">
      <path
        fill="currentColor"
        d="M215.8 85H264V3.6C255.7 2.5 227.1 0 193.8 0 124.3 0 76.7 42.4 76.7 120.3V192H0v91h76.7v229h94V283h73.6l11.7-91h-85.3v-62.7c0-26.3 7.3-44.3 45.1-44.3z"/>
    </svg>
    <svg
      v-else-if="icon === 'ig'"
      focusable="false"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 448 512">
      <path
        fill="currentColor"
        d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"/>
    </svg>
    <slot/>
  </bButton>
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
    },
    icon: {
      type: String,
      validator: (val) => ['', 'question', 'vk', 'fb', 'ig'].includes(val),
      default: ''
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

  > svg {
    height: 1rem;
    width: 1.1875rem;
    margin: 0 -0.5rem;
  }
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
