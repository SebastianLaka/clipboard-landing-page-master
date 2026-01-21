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
    <div class="snipets-content">
      <slot name="snipets-image" v-bind="snipetImage" />
      <slot name="snipet-feature" />
    </div>
  </section>
</template>
<style lang="scss" scoped>
  @use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px) {
  .site-snipets {
    @include flex-column-center;
    padding: 0 1em 0 0;
    gap: 3em 0;
    .snipets-content{
      @include flex-column;
      gap: 3em 0;
    }
  }
}
@media (min-width: 768px) {
  .site-snipets {
    gap: 5em 0;
  }
}
@media (min-width: 992px) {
  .site-snipets {
    grid-column: 1/ -1;
    .snipets-content{
      @include grid-12-col;
      align-content: center;
      gap: 0 5em;
    }
  }
}

</style>
