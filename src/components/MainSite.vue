<script setup>
import HeaderSite from './site-content/HeaderSite.vue'
import SiteButton from './site-content/SiteButton.vue'
</script>
<template>
  <HeaderSite>
    <template #logo="{ img, alt }">
      <div class="header-logo-area">
        <img :src="img" :alt="alt"/>
      </div>
      
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
        <SiteButton :class="'ios-button'">Download for iOS</SiteButton>
        <SiteButton :class="'mac-button'">Download for Mac</SiteButton>
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
    width: 100%;
    gap: 1.5em 0;
  }
  .ios-button{
    background-color: $green-500;
    border: .2em solid $green-500;
    border-color: $green-700;
    border-top: 0;
    &:hover{
      background-color: $green-0;
    }
  }
  .mac-button{
    background-color: $blue-100;
    border: .2em solid $blue-100;
    border-color: $blue-700;
    border-top: 0;
    &:hover{
      background-color: $blue-0;
    }
  }
}
@media (min-width: 768px){
  .header-logo-area{
    display: flex;
    justify-content: center;
    align-items: center;
    grid-column: 4/5;
    
  }
  .header-description{
    grid-column: 2/7;
    grid-row: 2/2;
    &__header{
      grid-column: 3/7;
    }
  }
  .header-buttons{
    grid-column: 2/7;
    width: 100%;
  }

}
</style>
