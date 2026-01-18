<template>
  <button type="submit" class="site-button">
    <slot>Base content</slot>
  </button>
</template>
<style lang="scss" scoped>
@use '../../assets/scss/colors.scss' as *;
@use '../../assets/scss/font.scss' as *;
@media (min-width: 375px) {
  .site-button {
    padding: 1em 1.5em;
    border-radius: 2em;
    font-weight: $secondary-weight;
    color: #fff;
    transition: background-color 0.3s ease-in-out;
  }
}
@media (min-width: 992px){
  .site-button{
    padding: 1em 4em;
  }
}
</style>
