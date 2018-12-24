<template>
  <bContainer>
    <Navbar
      :links="navLinks"
      :logo="logo"
      :phone="phones[0]">
      <Button type="primary">&nbsp;&nbsp;<small>Обратный звонок</small>&nbsp;&nbsp;</Button>
      <Button class="help-btn">?</Button>
    </Navbar>
    <nuxt role="main"/>
    <Footer
      :logo="logo"
      :copyright="copyright"
      :links="navLinks"
      :phones="phones"
      :working-time="workingTime">
      <Button size="small">VK</Button>
      <Button size="small">&nbsp;f&nbsp;</Button>
      <Button size="small">IN</Button>
    </Footer>
  </bContainer>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Button from '../components/Button.vue'
import bContainer from 'bootstrap-vue/src/components/layout/container'
import Footer from '../components/Footer'

export default {
  components: {
    Footer,
    Navbar,
    Button,
    bContainer
  },
  data: function () {
    return {
      navLinks: [
        { text: 'Link-1', to: 'link1' },
        { text: 'Link-2', to: 'link2' },
        { text: 'Link-3', to: 'link3' },
        { text: 'Link-4', to: 'link4' },
        { text: 'Link-5', to: 'link5' }
      ],
      logo: {
        url: 'https://via.placeholder.com/150x80?text=logo',
        description: 'logo'
      },
      copyright: 'test copyright',
      phones: [
        '+7 910 811 26 83',
        '+7 910 811 26 83'
      ],
      workingTime: [
        'Some days: 10:00-20:00',
        'Some days: 10:00-20:00'
      ]
    }
  }
}
</script>

<style src="../assets/grid.scss" lang="scss"/>

<style scoped lang="scss">
@import "../assets/customs";

.help-btn {
  font-weight: $font-weight-bold;

  &:not(:hover):not(:active) {
    color: $primary !important;
  }
}

nav button {
  margin-right: -999999px;
}

</style>
