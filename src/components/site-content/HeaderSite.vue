<script setup>
import logo from '../icons/logo.svg'
const imageSlotProps = {
  img: logo,
  alt: 'Header logo for site'
}
</script>
<template>
  <header class="header-site">
    <slot name="logo" v-bind="imageSlotProps"/>
    <slot name="content" />
    <slot name="actions" />
  </header>
</template>
<style lang="scss" scoped>
@media (min-width: 375px) {
    .header-site{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 1em;
        gap: 2em 0;
    }
}
</style>
