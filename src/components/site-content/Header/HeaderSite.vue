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
@use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px) {
  .header-site {
    @include flex-column-center;
    padding: 3em 1em 0 1em;
    gap: 3em 0;
    background-image: url(../../../assets/images/bg-header-mobile.png);
    background-repeat: no-repeat;
    background-position: right top;
  }
}
@media (min-width: 768px) {
  .header-site {
    @include grid-tablet;
    grid-template-rows: repeat(3, 1fr);
    background-image: url(../../../assets/images/bg-header-desktop.png);
  }
}
@media (min-width: 992px) {
  .header-site {
    @include grid-12-col;
  }
}
</style>
