<script setup>
import { reactive } from 'vue';
import HeaderSite from './site-content/HeaderSite.vue'
import SiteButton from './site-content/SiteButton.vue'

const styleDownloadButtons = reactive({
  iOS:{
    backgroundColor: 'hsl(171, 66%, 44%)',
    border: '.2em solid hsl(171, 66%, 44%)',
    borderColor: 'hsl(171, 66%, 35%)',
    borderTop: 0
  },
  Mac:{
    backgroundColor: 'hsl(233, 100%, 69%)',
    border: '.2em solid hsl(233, 100%, 69%)',
    borderColor: 'hsl(233, 92%, 63%)',
    borderTop: 0
  }
})
</script>
<template>
  <HeaderSite>
    <template #logo="{ img, alt }">
      <img :src="img" :alt="alt" />
    </template>
    <template #content>
      <div class="header-description">
        <h1 class="header-description__header">A history of everything you copy</h1>
        <p class="header-description__content">
          Clipboard allows you to track and organize everything you copy. Instantly access your
          clipboard on all your devices.
        </p>
      </div>
    </template>
    <template #actions>
      <div class="header-buttons">
        <SiteButton :style="styleDownloadButtons.iOS">Download for iOS</SiteButton>
        <SiteButton :style="styleDownloadButtons.Mac">Download for Mac</SiteButton>
      </div>
    </template>
  </HeaderSite>
</template>
<style lang="scss" scoped>
@use '../assets/scss/font' as *;
@use '../assets/scss/colors' as *;
@media (min-width: 375px) {
  .header-description {
    &__header {
      font-size: 2rem;
      text-align: center;
      font-weight: $secondary-weight;
      color: $gray-700;
    }
    &__content {
      text-align: center;
      color: $gray-500;
    }
  }
  .header-buttons {
    display: flex;
    flex-direction: column;
    justify-self: start;
    width: 100%;
    gap: 1.5em 0;
  }
}
</style>
