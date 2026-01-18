<script setup></script>
<template>
  <section class="site-snipets">
    <slot name="snipets-header" />
    <slot name="snipets-image" />
    <slot name="snipets-features" />
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
    gap: 1.25em 0;
  }
}
</style>
