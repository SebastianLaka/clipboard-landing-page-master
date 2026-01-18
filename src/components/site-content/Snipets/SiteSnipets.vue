<script setup>
import SnipetImage from '../../../assets/images/image-computer.png'
const snipetImage = {
  img: SnipetImage,
  alt: 'Snipet computer image',
}
</script>
<template>
  <section class="site-snipets">
    <slot name="snipets-header" />
    <slot name="snipets-image" v-bind="snipetImage" />
    <slot name="snipet-feature" />
  </section>
</template>
<style lang="scss" scoped>
@media (min-width: 375px) {
  .site-snipets {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 1em;
    gap: 3em 0;
  }
}
@media (min-width: 768px) {
  .site-snipets {
    gap: 5em 0;
  }
}
</style>
