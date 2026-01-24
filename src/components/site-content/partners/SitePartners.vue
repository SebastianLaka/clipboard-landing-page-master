<script setup>
import googleLogo from '../../../assets/images/logo-google.png';
import ibmLogo from '../../../assets/images/logo-ibm.png';
import microsoftLogo from '../../../assets/images/logo-microsoft.png';
import hpLogo from '../../../assets/images/logo-hp.png';
import vectorGraphicsLogo from '../../../assets/images/logo-vector-graphics.png';

const partnersLogos = { 
    google:{
        id: 1,
        img: googleLogo,
        alt: 'Partner logo Google'
    },
    ibm: {
        id: 2,
        img: ibmLogo,
        alt: 'Partner logo ibm'
    },
    microsoft: {
        id: 3,
        img: microsoftLogo,
        alt: 'Partner hp logo'
    },
    hp: {
        id: 4,
        img: hpLogo,
        alt: 'Partner hp logo'
    },
    vectorGraphics: {
        id: 5,
        img: vectorGraphicsLogo,
        alt: 'Partner vector graphics logo'
    }
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
@use '../../../assets/scss/mixins.scss' as *;
@media (min-width: 375px){
    .partners-logos-main{
        @include flex-column-center;
        gap: 3.25em 0;
    }
}
@media (min-width: 992px){
    .partners-logos-main{
        flex-direction: row;
        justify-content: space-around;
    }
}
</style>