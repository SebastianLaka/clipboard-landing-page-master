<script setup>
import imageDevices from '../../../assets/images/image-devices.png'
const clipboartImage = {
  img: imageDevices,
  alt: 'Devices with wallpaper',
}
</script>
<template>
  <section class="clipboard-section">
    <div class="clipboard-main">
      <slot name="header" />
    </div>
    <slot name="clipboard-image" v-bind="clipboartImage" />
  </section>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use "sass:map";
@media (min-width: 375px) {
  .clipboard-section {
    @include flex-column;
    gap: map.get($site-gap,'shared');
    .clipboard-main{
        @include flex-column-center;
        gap: map.get($site-gap, 'section-content');
    }
  }
}
@media (min-width: 992px){
    .clipboard-section{
        @include section-grid($columns: 12, $rows: 1);
        .clipboard-main{
            grid-column: 3/11;
            grid-row: 1/1;
        }
    }
}
</style>
