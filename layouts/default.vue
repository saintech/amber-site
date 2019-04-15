<template>
  <bContainer>
    <ContactModal v-model="showContactModal"/>
    <Navbar
      :links="navLinks"
      :logo="logo"
      :phone="phones[0]">
      <Button
        type="primary"
        @click="showContactModal = true">&nbsp;&nbsp;Обратный звонок&nbsp;&nbsp;</Button>
      <Button
        class="icon-btn"
        icon="question"/>
    </Navbar>
    <nuxt role="main"/>
    <Footer
      :logo="logoFooter"
      :copyright="copyright"
      :links="navLinks"
      :phones="phones"
      :working-time="workingTime">
      <Button
        class="icon-btn"
        size="small"
        icon="vk"/>
      <Button
        class="icon-btn"
        size="small"
        icon="fb"/>
      <Button
        class="icon-btn"
        size="small"
        icon="ig"/>
    </Footer>
  </bContainer>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Button from '../components/Button.vue'
import ContactModal from '../components/ContactModal'
import bContainer from 'bootstrap-vue/src/components/layout/container'
import Footer from '../components/Footer'

export default {
  components: {
    Footer,
    Navbar,
    Button,
    ContactModal,
    bContainer
  },
  data: function () {
    return {
      navLinks: [
        { text: 'Проекты', to: '/' },
        { text: 'Готовые решения', to: '/' },
        { text: 'О нас', to: '/' },
        { text: 'Контакты', to: '/' }
      ],
      logo: {
        url: require('../assets/images/logo-header.png'),
        description: 'logo'
      },
      logoFooter: {
        url: require('../assets/images/logo-footer.png'),
        description: 'logo'
      },
      copyright: '2018 Amber Group',
      phones: [
        '+7 910 811 26 83',
        '+7 910 811 26 83'
      ],
      workingTime: [
        'Some days: 10:00-20:00',
        'Some days: 10:00-20:00'
      ],
      showContactModal: false
    }
  }
}
</script>

<style lang="scss">
@import "../assets/customs";
@import "../assets/bootstrap/bootstrap";
@import '~bootstrap-vue/dist/bootstrap-vue';
</style>

<style scoped lang="scss">
@import "../assets/customs";

.icon-btn {
  font-weight: $font-weight-bold !important;

  &:not(:hover):not(:active) {
    color: $primary !important;
  }
}

nav button {
  margin-right: -999999px;
}

</style>
