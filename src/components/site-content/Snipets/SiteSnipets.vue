<script setup>
import SnipetImage from '../../../assets/images/image-computer.png'
const snipetImage = {
  img: SnipetImage,
  alt: 'Computer with wallpaper',
}
</script>
<template>
  <section class="site-snipets">
    <slot name="snipets-header" />
    <div class="snipets-content">
      <slot name="snipets-image" v-bind="snipetImage" />
      <slot name="snipet-feature" />
    </div>
  </section>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/breakpoints.scss' as *;
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use "sass:map";
@media (min-width: $mobile) {
  .site-snipets {
    @include flex-column-center;
    gap: map.get($site-gap, 'shared');
    .snipets-content {
      @include flex-column;
      gap: map.get($site-gap, 'shared');
    }
  }
}
@media (min-width: $tablet) {
  .site-snipets {
    gap: 5em 0;
  }
}
@media (min-width: $desktop-small) {
  .site-snipets {
    .snipets-content {
      @include section-grid($columns: 12, $rows: 1);
      gap: 0 5em;
    }
  }
}
</style>
