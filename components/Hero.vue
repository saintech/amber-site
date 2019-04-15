<template>
  <div>
    <bRow>
      <bCol>
        <img
          :src="logo"
          class="logo"
          alt="logo">
      </bCol>
    </bRow>
    <bRow class="text-row">
      <bCol
        md="3"
        sm="2">
        <img
          :src="illustration"
          class="illustration"
          alt="illustration">
      </bCol>
      <bCol
        md="6"
        sm="7"
        tag="article">
        <h2 class="title">{{ title }}</h2>
        <p><slot/></p>
        <Button
          :to="to"
          size="large"
          class="about">Узнать больше</Button>
      </bCol>
    </bRow>
  </div>
</template>

<script>
import bRow from 'bootstrap-vue/src/components/layout/row'
import bCol from 'bootstrap-vue/src/components/layout/col'
import bLink from 'bootstrap-vue/src/components/link/link'
import Button from './Button'

export default {
  name: 'Hero',
  components: {
    bRow,
    bCol,
    Button,
    bLink
  },
  props: {
    logo: {
      type: String,
      default: ''
    },
    illustration: {
      type: String,
      default: ''
    },
    title: {
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

.logo {
  display: block;
  max-width: 100%;
  height: auto;
  margin: 13% auto 6% auto;
}

.text-row {
  margin-bottom: 3rem;
}

.illustration {
  max-width: 170%;
  height: auto;
  margin-left: -70%;
}

.title {
  font-size: $h3-font-size;
  text-transform: uppercase;
  margin-top: 1.5rem;
}

.about {
  width: 15rem;
}
</style>
