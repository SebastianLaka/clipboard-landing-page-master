<script setup>
import HeaderSite from './site-content/Header/HeaderSite.vue'
import SiteSnipets from './site-content/Snipets/SiteSnipets.vue'
import SiteClipboard from './site-content/clipboard/SiteClipboard.vue'
import SiteWorkflow from './site-content/workflow/SiteWorkflow.vue'
import SitePartners from './site-content/partners/SitePartners.vue'
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
    <SiteClipboard>
      <template #header>
        <h1 class="clipboard-main__header">Access Clipboard anywhere</h1>
        <p class="clipboard-main__description">
          Whether you’re on the go, or at your computer, you can access all your Clipboard snippets
          in a few simple clicks.
        </p>
      </template>
      <template #clipboard-image="{ img, alt }">
        <img :src="img" :alt="alt" class="clipboard-main__img" />
      </template>
    </SiteClipboard>
    <SiteWorkflow>
      <template #workflow-header>
        <div class="workflow-header-content">
          <h1 class="workflow-header-content__header">Supercharge your workflow</h1>
          <p class="workflow-header-content__description">
            We’ve got the tools to boost your productivity.
          </p>
        </div>
      </template>
      <template #workflow-blacklist="{ img, alt }">
        <div class="blacklist-workflow">
          <img :src="img" :alt="alt" class="blacklist-workflow__icon" />
          <h2 class="blacklist-workflow__header">Create blacklists</h2>
          <p class="blacklist-workflow__description">
            Ensure sensitive information never makes its way to your clipboard by excluding certain
            sources.
          </p>
        </div>
      </template>
      <template #workflow-text="{ img, alt }">
        <div class="text-workflow">
          <img :src="img" :alt="alt" class="text-workflow__icon" />
          <h2 class="text-workflow__header">Plain text snipets</h2>
          <p class="text-workflow__description">
            Remove unwanted formatting from copied text for a consistent look.
          </p>
        </div>
      </template>
      <template #workflow-preview="{ img, alt }">
        <div class="preview-workflow">
          <img :src="img" :alt="alt" class="preview-workflow__icon" />
          <h2 class="preview-workflow__header">Sneak preview</h2>
          <p class="preview-workflow__description">
            Quick preview of all snippets on your Clipboard for easy access.
          </p>
        </div>
      </template>
    </SiteWorkflow>
    <SitePartners>
      <template #partners-list="{img, alt}">
        <img :src="img" :alt="alt">
      </template>
    </SitePartners>
  </main>
</template>
<style lang="scss" scoped>
@use '../assets/scss/font' as *;
@use '../assets/scss/colors' as *;
@use '../assets//scss/mixins.scss' as *;
@media (min-width: 375px) {
  .site-container {
    @include flex-column;
    padding: 0 1em;
    gap: 10em 0;
    .header-description {
      &__header {
        font-size: 3rem;
        text-align: center;
        font-weight: $secondary-weight;
      }
      &__content {
        text-align: center;
      }
    }
    .header-buttons {
      @include flex-column;
      width: 100%;
      gap: 1.5em 0;
      &__ios-button {
        @include site-button(
          $background-color: $green-500,
          $border: 0.2em solid $green-700,
          $border-color: $green-700,
          $border-top: 0
        );
        &:hover {
          background-color: $green-0;
        }
      }
      &__mac-button {
        @include site-button(
          $background-color: $blue-100,
          $border: 0.2em solid $blue-100,
          $border-color: $blue-700,
          $border-top: 0
        );
        &:hover {
          background-color: $blue-0;
        }
      }
    }
  }
  .header-snipets {
    @include flex-column;
    align-items: center;
    gap: 1.25em 0;
    &__header {
      font-size: 2rem;
      font-weight: $secondary-weight;
      text-align: center;
    }
    &__description {
      text-align: center;
    }
  }
  .snipets-features-main {
    @include flex-column;
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
      }
    }
  }
  .clipboard-main {
    &__header {
      font-size: 2rem;
      font-weight: $secondary-weight;
      text-align: center;
    }
    &__description {
      text-align: center;
      padding: 0 1.25em;
    }
  }
  .workflow-header-content {
    @include flex-column;
    grid-column: 3/11;
    gap: 0.5em 0;
    &__header {
      font-size: 2rem;
      font-weight: $secondary-weight;
    }
  }
  .blacklist-workflow,
  .text-workflow,
  .preview-workflow {
    @include flex-column-center;
    padding: 0 3.5em;
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
  .blacklist-workflow,
  .text-workflow,
  .preview-workflow {
    gap: 1em;
    &__header {
      font-size: 2rem;
      font-weight: $secondary-weight;
    }
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
      @include grid-12-col;
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
    .clipboard-main {
      &__img {
        grid-row: 2/2;
        grid-column: 3/11;
        justify-self: stretch;
      }
    }
    .workflow-header-content {
      grid-column: 4/10;
    }
    .blacklist-workflow {
      grid-column: 1/6;
    }
    .text-workflow {
      grid-column: 7/13;
    }
    .preview-workflow {
      grid-column: 4/10;
    }
  }
}
@media (min-width: 1350px) {
  .site-container {
    .header-description{
      &__content{
          padding: 0 12em;
      }
    }
    .header-snipets{
      &__description{
        width: 80ch;
      }
    }
    .snipet-image {
      justify-self: stretch;
    }
    .clipboard-main {
      &__description {
        width: 65ch;
      }
    }
    .blacklist-workflow {
      grid-column: 1/4;
      &__description {
        padding: 0 1.25em;
      }
    }
    .text-workflow {
      grid-column: 5/9;
      &__description {
        padding: 0 1.25em;
      }
    }
    .preview-workflow {
      grid-column: 9/13;
      &__description {
        padding: 0 2em;
      }
    }
  }
}
</style>
