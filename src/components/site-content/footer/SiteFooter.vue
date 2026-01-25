<script setup>
import logo from '../../icons/logo.svg'
const footerLogo = {
  img: logo,
  alt: 'Footer logo for site',
}
</script>
<template>
<footer class="site-footer">
    <slot name="footer-logo" v-bind="footerLogo"></slot>
    <slot name="footer-links"></slot>
    <slot name="footer-social-media"></slot>
</footer>
</template>
<style lang="scss" scoped>
</style>