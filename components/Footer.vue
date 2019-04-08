<template>
  <footer>
    <bRow>
      <bCol
        sm="4"
        lg="2">
        <img
          :src="logo.url"
          :alt="logo.description">
        <p><small>&copy; {{ copyright }}</small></p>
      </bCol>
      <bCol
        offset-sm="1"
        sm="4"
        offset-lg="0"
        lg="2">
        <ul class="navigation">
          <li
            v-for="link in links"
            :key="link.to">
            <bLink :to="link.to">{{ link.text }}</bLink>
          </li>
        </ul>
      </bCol>
      <bCol
        sm="4"
        lg>
        <h4>Телефон:</h4>
        <ul class="phone-numbers">
          <li
            v-for="(phone, index) in phones"
            :key="index">{{ phone }}</li>
        </ul>
      </bCol>
      <bCol
        offset-sm="1"
        sm="4"
        offset-lg="0"
        lg>
        <h4>Мы работаем:</h4>
        <ul class="working-time">
          <li
            v-for="(line, index) in workingTime"
            :key="index">{{ line }}</li>
        </ul>
      </bCol>
      <bCol
        offset-lg="4"
        lg="5"
        offset-xl="0"
        xl="2">
        <bRow>
          <bCol cols="auto">
            <h4>Мы в соцсетях:</h4>
          </bCol>
          <bCol cols="auto">
            <slot/>
          </bCol>
        </bRow>
      </bCol>
    </bRow>
  </footer>
</template>

<script>
import bRow from 'bootstrap-vue/src/components/layout/row'
import bCol from 'bootstrap-vue/src/components/layout/col'
import bLink from 'bootstrap-vue/src/components/link/link'
import Button from './Button'

export default {
  name: 'Footer',
  components: {
    bRow,
    bCol,
    Button,
    bLink
  },
  props: {
    logo: {
      type: Object,
      default: () => ({ url: '', description: '' })
    },
    copyright: {
      type: String,
      default: '[empty]'
    },
    links: {
      type: Array,
      default: () => [{ text: '[empty]', to: '404' }]
    },
    phones: {
      type: Array,
      validator: (val) => val.every((i) => typeof i === 'string'),
      default: () => ['[empty]']
    },
    workingTime: {
      type: Array,
      validator: (val) => val.every((i) => typeof i === 'string'),
      default: () => ['[empty]']
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";

footer {
  background-color: $white;
  margin: 0 -50%;
  padding: 4rem 50%;

  h4 {
    font-size: $font-size-base * 1.125;
    font-weight: $font-weight-bold;
  }
}

.navigation, .phone-numbers, .working-time {
  padding-left: 0;
  list-style: none;
}
</style>
