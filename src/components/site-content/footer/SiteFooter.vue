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
    id: 1,
    img: instagramIcon,
    alt: 'Instagram icon in footer',
  },
]
</script>
<template>
  <footer class="site-footer">
    <slot name="footer-logo" v-bind="footerLogo"></slot>
    <div class="links-box">
      <slot
        name="footer-links"
        v-for="footerLink in footerLinks"
        :key="footerLink.id"
        :linkName="footerLink.linkName"
        v-bind="footerLink"
      />
    </div>
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
@use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px){
    .site-footer{
        @include flex-column-center;
        gap: 2em 0;
        .links-box{
            @include flex-column-center;
            gap: 1em 0;
        }
        .social-media-box{
            display: flex;
            flex-direction: row;
            gap: 0 2em;
        }
    }
}
</style>
