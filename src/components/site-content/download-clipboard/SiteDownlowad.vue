<template>
  <section class="download-section">
    <slot name="download-content" />
  </section>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px){
    .download-section{
        @include flex-column-center;
    }
}
</style>