<script setup>
import logo from '../../icons/logo.svg'
const imageSlotProps = {
  img: logo,
  alt: 'Header logo for site',
}
</script>
<template>
  <header class="header-site">
    <slot name="logo" v-bind="imageSlotProps" />
    <slot name="content" />
    <slot name="actions" />
  </header>
</template>
<style lang="scss" scoped>
@media (min-width: 375px) {
  .header-site {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 3em 1em 0 1em;
    gap: 2em 0;
    background-image: url(../../../assets/images/bg-header-mobile.png);
    background-repeat: no-repeat;
    background-position: right top;
  }
}
@media (min-width: 768px) {
  .header-site {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    grid-template-rows: repeat(3, 1fr);
    background-image: url(../../../assets/images/bg-header-desktop.png);
  }
}
@media (min-width: 992px) {
  .header-site {
    grid-column: 1/ -1;
  }
}
</style>
