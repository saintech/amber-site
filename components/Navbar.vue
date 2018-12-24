<template>
  <bNavbar
    toggleable="sm"
    class="row align-items-center">
    <bNavbarNav class="col">
      <bNavItem
        v-for="link in links"
        :key="link.to"
        :to="link.to"
        class="text-nowrap text-uppercase">
        {{ link.text }}
      </bNavItem>
    </bNavbarNav>
    <bNavbarBrand
      v-if="logo.url.length > 0"
      to="/"
      class="col-auto">
      <img
        :src="logo.url"
        :alt="logo.description"
        class="brand-image">
    </bNavbarBrand>
    <div class="w-100 d-sm-none"/>
    <div class="col text-md-right">
      <bNavText
        v-if="phone !== ''"
        class="phone">
        <strong>{{ phone }}</strong>
      </bNavText>
      <span class="right-content">
        <slot/>
      </span>
    </div>
  </bNavbar>
</template>

<script>
import bCol from 'bootstrap-vue/src/components/layout/col'
import bNavbar from 'bootstrap-vue/src/components/navbar/navbar'
import bNavbarNav from 'bootstrap-vue/src/components/navbar/navbar-nav'
import bNavbarBrand from 'bootstrap-vue/src/components/navbar/navbar-brand'
import bNavItem from 'bootstrap-vue/src/components/nav/nav-item'
import bNavText from 'bootstrap-vue/src/components/nav/nav-text'
import bButton from 'bootstrap-vue/src/components/button/button'

export default {
  name: 'Navbar',
  components: {
    bCol,
    bNavbar,
    bNavbarNav,
    bNavbarBrand,
    bNavItem,
    bNavText,
    bButton
  },
  props: {
    links: {
      type: Array,
      default: () => [{ text: '[empty]', to: '404' }]
    },
    logo: {
      type: Object,
      default: () => ({ url: '', description: '' })
    },
    phone: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";
@import "~bootstrap/scss/navbar";
@import "~bootstrap/scss/nav";
@import "~bootstrap/scss/utilities/spacing";
@import "~bootstrap/scss/utilities/text";
@import "~bootstrap/scss/utilities/display";
@import "~bootstrap/scss/utilities/sizing";
@import "~bootstrap/scss/utilities/align";
@import "~bootstrap/scss/buttons";
@import "~bootstrap/scss/grid";
@import "~bootstrap/scss/type";

.navbar-brand {
  text-align: center;
}

.nav-link {
  padding-left: 0 !important;
  padding-right: ($navbar-nav-link-padding-x * 2) !important;
  text-decoration: none !important;
  @include hover-focus {
    text-decoration: underline !important;
  }
}

.brand-image {
  height: 5rem;
}

.phone {
  margin-right: ($spacer * .5);
}

.right-content {
  white-space: nowrap;

  * {
    margin-right: ($spacer * .5);
  }

  > *:last-child {
    margin-right: 0;
  }

  > button {
    vertical-align: baseline;
  }
}
</style>
