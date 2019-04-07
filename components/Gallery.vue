<template>
  <div class="placeholder">
    <no-ssr placeholder="Loading...">
      <flickity
        ref="flickity"
        :options="flickityOptions"
        class="gallery">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image.url"
          :alt="image.description"
          class="image"
          @load="$refs.flickity.reloadCells()">
      </flickity>
    </no-ssr>
  </div>
</template>

<script>
import Vue from '../node_modules/vue'

if (process['client']) {
  const Flickity = require('vue-flickity').default
  Vue.component('Flickity', Flickity)
}

export default {
  name: 'Gallery',
  components: {
  },
  props: {
    images: {
      type: Array,
      default: () => [{ url: 'data:image/gif;base64,R0lGODdhAQABAPAAAL6+vgAAACwAAAAAAQABAAACAkQBADs=', description: '[empty]' }]
    }
  },
  data: function () {
    return {
      flickityOptions: {
        draggable: true,
        prevNextButtons: true,
        pageDots: false,
        cellAlign: 'left',
        contain: true,
        groupCells: '80%',
        lazyLoad: true
      }
    }
  },
  mounted: function () {
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";
@import "../assets/bootstrap/mixins/breakpoints";

.placeholder {
  margin-bottom: $grid-gutter-width;
}

.gallery {
  position: absolute;
  width: 100%;
  left: 0;
}

.image {
  display: block;
  margin-right: $grid-gutter-width;
}

@include media-breakpoint-up(xs) {
  .placeholder, .image {
    height: 14rem;
  }
}

@include media-breakpoint-up(sm) {
  .placeholder, .image {
    height: 22rem;
  }
}

@include media-breakpoint-up(md) {
  .placeholder, .image {
    height: 35rem;
  }
}

@include media-breakpoint-up(lg) {
  .placeholder, .image {
    height: 42rem;
  }
}
</style>
