<script setup>
import logo from '../../icons/logo.svg'
import facebookIcon from '../../icons/icon-facebook.svg'
import twitterIcon from '../../icons/icon-twitter.svg'
import instagramIcon from '../../icons/icon-instagram.svg'
const footerLogo = {
  img: logo,
  alt: 'Footer logo for site',
}
const footerLinks = [
  {
    id: 1,
    linkName: 'FAQ',
  },
  {
    id: 2,
    linkName: 'Contact us',
  },
  {
    id: 3,
    linkName: 'Privacy Policy',
  },
  {
    id: 4,
    linkName: 'Press Kit',
  },
  {
    id: 5,
    linkName: 'Install Guide',
  },
]
const footerMedias = [
  {
    id: 1,
    img: facebookIcon,
    alt: 'Facebook icon in footer',
  },
  {
    id: 2,
    img: twitterIcon,
    alt: 'Twitter icon in footer',
  },
  {
    id: 3,
    img: instagramIcon,
    alt: 'Instagram icon in footer',
  },
]
</script>
<template>
  <footer class="site-footer">
    <slot name="footer-logo" v-bind="footerLogo"></slot>
    <ul class="links-box">
      <slot
        name="footer-links"
        v-for="footerLink in footerLinks"
        :key="footerLink.id"
        :linkName="footerLink.linkName"
        v-bind="footerLink"
      />
    </ul>
    <div class="social-media-box">
      <slot
        name="footer-social-media"
        v-for="footerMedia in footerMedias"
        :key="footerMedia.id"
        :img="footerMedia.img"
      />
    </div>
  </footer>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/breakpoints.scss' as *;
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use 'sass:map';
@media (min-width: $mobile) {
  .site-footer {
    @include flex-column-center;
    gap: map.get($site-gap, 'shared');
    .links-box {
      @include flex-column-center;
      gap: map.get($site-gap, 'section-content');
    }
    .social-media-box {
      display: flex;
      gap: 0 2em;
    }
  }
}
@media (min-width: $desktop-small) {
  .site-footer {
    @include section-grid($columns: 12, $rows: 1);
    .links-box {
      @include section-grid($columns: 3, $rows: 2);
      grid-auto-flow: column;
      grid-column: 3/11;
      flex-direction: unset;
      justify-self: start;
      gap: 1em 4.9em;
    }
    .social-media-box {
      grid-column: 11/-1;
      justify-self: end;
    }
  }
}
@media (min-width: $desktop-wide) {
  .site-footer {
    .links-box {
      @include section-grid($columns: 5, $rows: 1);
      grid-auto-flow: row;
      justify-self: center;
  
    }
  }
}
</style>
