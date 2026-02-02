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
@use '../../../assets/scss/breakpoints.scss' as *;
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use "sass:map";
@media (min-width: $mobile) {
  .workflow-main {
    @include flex-column-center;
    text-align: center;
    gap: map.get($site-gap, 'shared');
  }
}
@media (min-width: $desktop-small) {
  .workflow-main {
    @include section-grid($columns: 12, $rows: 1);
    place-items: center;
    align-items: start;
  }
}
@media (min-width: $desktop-wide) {
  .workflow-main {
    gap: 4em;
  }
}
</style>
