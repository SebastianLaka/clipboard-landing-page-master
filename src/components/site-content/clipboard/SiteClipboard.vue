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
@media (min-width: 375px) {
  .clipboard-section {
    @include flex-column;
    gap: 4em 0;
    .clipboard-main{
        @include flex-column-center;
        gap: 1em 0;
    }
  }
}
@media (min-width: 992px){
    .clipboard-section{
        @include grid-12-col;
        .clipboard-main{
            grid-column: 3/11;
            grid-row: 1/1;
        }
    }
}
</style>
