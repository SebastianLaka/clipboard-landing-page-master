<script setup>
import HeaderSite from './site-content/Header/HeaderSite.vue'
import SiteSnipets from './site-content/Snipets/SiteSnipets.vue'
import SiteButton from './site-content/SiteButton.vue'
</script>
<template>
  <main class="site-container">
    <HeaderSite>
      <template #header-logo="{ img, alt }">
          <img :src="img" :alt="alt" class="header-logo" />
      </template>
      <template #header-content>
        <div class="header-description">
          <h1 class="header-description__header">A history of everything you copy</h1>
          <p class="header-description__content">
            Clipboard allows you to track and organize everything you copy. Instantly access your
            clipboard on all your devices.
          </p>
        </div>
      </template>
      <template #header-actions>
        <div class="header-buttons">
          <SiteButton class="header-buttons__ios-button">Download for iOS</SiteButton>
          <SiteButton class="header-buttons__mac-button">Download for Mac</SiteButton>
        </div>
      </template>
    </HeaderSite>
    <SiteSnipets>
      <template #snipets-header>
        <div class="header-snipets">
          <h2 class="header-snipets__header">Keep track of your snippets</h2>
          <p class="header-snipets__description">
            Clipboard instantly stores any item you copy in the cloud, meaning you can access your
            snippets immediately on all your devices. Our Mac and iOS apps will help you organize
            everything.
          </p>
        </div>
      </template>
      <template #snipets-image="{ img, alt }">
        <img :src="img" :alt="alt" class="snipet-image" />
      </template>
      <template #snipet-feature>
        <div class="snipets-features-main">
          <div class="feature-search">
            <h2 class="feature-search__title">Quick Search</h2>
            <p class="feature-search__about">
              Easily search your snippets by content, category, web address, application, and more.
            </p>
          </div>
          <div class="feature-cloud">
            <h2 class="feature-cloud__title">iCloud Sync</h2>
            <p class="feature-cloud__about">
              Instantly saves and syncs snippets across all your devices.
            </p>
          </div>
          <div class="feature-history">
            <h2 class="feature-history__title">Complete History</h2>
            <p class="feature-history__about">
              Retrieve any snippets from the first moment you started using the app.
            </p>
          </div>
        </div>
      </template>
    </SiteSnipets>
  </main>
</template>
<style lang="scss" scoped>
@use '../assets/scss/font' as *;
@use '../assets/scss/colors' as *;
@media (min-width: 375px) {
  .site-container {
    display: flex;
    flex-direction: column;
    gap: 5em 0;
    .header-description {
      &__header {
        font-size: 3rem;
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
      &__ios-button {
        background-color: $green-500;
        border: 0.2em solid $green-500;
        border-color: $green-700;
        border-top: 0;
        transition: background-color 0.3s ease-in-out;
        &:hover {
          background-color: $green-0;
        }
      }
      &__mac-button {
        background-color: $blue-100;
        border: 0.2em solid $blue-100;
        border-color: $blue-700;
        border-top: 0;
        transition: background-color 0.3s ease-in-out;
        &:hover {
          background-color: $blue-0;
        }
      }
    }
  }
  .header-snipets {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.25em 0;
    &__header {
      font-size: 2rem;
      font-weight: $secondary-weight;
      color: $gray-700;
      text-align: center;
    }
    &__description {
      text-align: center;
      color: $gray-500;
    }
  }
  .snipets-features-main {
    display: flex;
    flex-direction: column;
    gap: 2.5em 0;
    .feature-search,
    .feature-cloud,
    .feature-history {
      &__title {
        font-size: 2rem;
        font-weight: $secondary-weight;
        text-align: center;
      }
      &__about {
        text-align: center;
        color: $gray-700;
      }
    }
  }
}
@media (min-width: 768px) {
  .header-logo {
    display: flex;
    justify-content: center;
    align-items: center;
    grid-column: 4/5;
  }
  .header-description {
    grid-column: 2/7;
    grid-row: 2/2;
    &__header {
      grid-column: 3/7;
    }
  }
  .header-buttons {
    grid-column: 2/7;
    width: 100%;
  }
  .header-snipets {
    gap: 1.5em 0;
  }
}
@media (min-width: 992px) {
  .site-container {
    .header-logo {
      grid-column: 7/7;
      transform: translateX(-50%);
    }
    .header-description {
      grid-column: 3/11;
    }
    .header-buttons {
      flex-direction: row;
      grid-column: 3/11;
      justify-content: space-evenly;
      gap: 0 1em;
    }
    .header-snipets {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      &__header {
        grid-column: 4/10;
      }
      &__description {
        grid-column: 3/11;
      }
    }
    .snipet-image {
      grid-column: 1/8;
      transform: translateX(-28px);
    }
    .snipets-features-main {
      justify-content: center;
      grid-column: 8/12;
      .feature-search,
      .feature-cloud,
      .feature-history {
        &__title {
          font-size: 1.75rem;
        }
        &__title,
        &__about {
          text-align: left;
        }
      }
    }
  }
}
@media (min-width: 1350px) {
  .snipet-image {
    justify-self: stretch;
  }
}
</style>
