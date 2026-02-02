<script setup>
import logo from '../../icons/logo.svg'
const headerLogo = {
  img: logo,
  alt: 'Header logo for site',
}
</script>
<template>
  <header class="header-site">
    <slot name="header-logo" v-bind="headerLogo" />
    <slot name="header-content" />
    <slot name="header-actions" />
  </header>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/breakpoints.scss' as *;
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use "sass:map";
@media (min-width: $mobile) {
  .header-site {
    @include flex-column-center;
    padding: 3em 1em 0 1em;
    gap: map.get($site-gap, 'shared');
    background-image: url(../../../assets/images/bg-header-mobile.png);
    background-repeat: no-repeat;
    background-position: right top;
  }
}
@media (min-width: $tablet) {
  .header-site {
    background-image: url(../../../assets/images/bg-header-desktop.png);
    @include section-grid(
      $columns: 7,
      $rows: 3,
    );
    align-items: center;
  }
}
@media (min-width: $desktop-small) {
  .header-site {
    @include section-grid($columns: 12, $rows: 2)
  }
}
</style>
