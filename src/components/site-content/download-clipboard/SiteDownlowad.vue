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
        gap: 4em 0;
    }
}
@media (min-width: 768px) {
  .download-section {
    @include section-grid(
      $columns: 7,
      $rows: 3,
    );
  }
}
@media (min-width: 992px) {
  .download-section{
    @include section-grid($columns: 12, $rows: 2);
  }
}
</style>