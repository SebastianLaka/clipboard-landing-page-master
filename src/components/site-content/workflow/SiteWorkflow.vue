<script setup>
import blacklistIcon from '../../icons/icon-blacklist.svg'
import textIcon from '../../icons/icon-text.svg'
import previewIcon from '../../icons/icon-preview.svg'

const workflowIcons = {
  blacklist: {
    img: blacklistIcon,
    alt: 'Icon with list for blacklist',
  },
  text: {
    img: textIcon,
    alt: 'Icon with A letter and cursor',
  },
  preview: {
    img: previewIcon,
    alt: 'Icon with eye',
  },
}
</script>
<template>
  <section class="workflow-main">
    <slot name="workflow-header" />
    <slot name="workflow-blacklist" v-bind="workflowIcons.blacklist" />
    <slot name="workflow-text" v-bind="workflowIcons.text"></slot>
    <slot name="workflow-preview" v-bind="workflowIcons.preview"></slot>
  </section>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px) {
  .workflow-main {
    @include flex-column-center;
    text-align: center;
    gap: 3em 0;
  }
}
@media (min-width: 992px) {
  .workflow-main {
    @include grid-12-col;
    place-items: center;
     align-items: start;
  }
}
@media (min-width: 1350px) {
  .workflow-main {
    gap: 4em;
    
  }
}
</style>
