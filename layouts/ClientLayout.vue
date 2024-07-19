<!-- layouts/layout.vue -->

<template>
    <div>
      <HeaderComponent />
      <nuxt />
      <AdsComponent />
    </div>
  </template>
  
  <script>
  import HeaderComponent from '~/components/HeaderComponent.vue';
  import AdsComponent from '~/components/AdsComponent.vue';
import Adcash from '~/components/Adcash.vue';
  
  export default {
    name: 'ClientLayout',
    components: {
      HeaderComponent,
      AdsComponent,
      // Adcash,
    },
  };
  </script>
 