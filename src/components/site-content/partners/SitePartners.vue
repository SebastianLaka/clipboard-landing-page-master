<script setup>
import googleLogo from '../../../assets/images/logo-google.png'
import ibmLogo from '../../../assets/images/logo-ibm.png'
import microsoftLogo from '../../../assets/images/logo-microsoft.png'
import hpLogo from '../../../assets/images/logo-hp.png'
import vectorGraphicsLogo from '../../../assets/images/logo-vector-graphics.png'

const partnersLogos = {
  google: {
    id: 1,
    img: googleLogo,
    alt: 'Partner logo Google',
  },
  ibm: {
    id: 2,
    img: ibmLogo,
    alt: 'Partner logo ibm',
  },
  microsoft: {
    id: 3,
    img: microsoftLogo,
    alt: 'Partner hp logo',
  },
  hp: {
    id: 4,
    img: hpLogo,
    alt: 'Partner hp logo',
  },
  vectorGraphics: {
    id: 5,
    img: vectorGraphicsLogo,
    alt: 'Partner vector graphics logo',
  },
}
</script>
<template>
  <section class="partners-logos-main">
    <slot
      name="partners-list"
      v-for="partnerLogo in partnersLogos"
      :key="partnerLogo.id"
      :alt="partnerLogo.alt"
      v-bind="partnerLogo"
    />
  </section>
</template>
<style lang="scss" scoped>
@use '../../../assets/scss/breakpoints.scss' as *;
@use '../../../assets/scss/mixins.scss' as *;
@use '../../../assets/scss/maps.scss' as *;
@use "sass:map";
@media (min-width: $mobile) {
  .partners-logos-main {
    @include flex-column-center;
    gap: map.get($site-gap, 'shared');
  }
}
@media (min-width: $tablet) {
  .partners-logos-main {
    @include section-grid($columns: 3, $rows: 1);
    justify-items: center;
  }
}
@media (min-width: $desktop-large) {
  .partners-logos-main {
    @include section-grid($columns: 5, $rows: 1);
  }
}

</style>
