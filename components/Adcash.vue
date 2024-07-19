<template>
    <div :id="adId"></div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        adId: 'bg-ssp-9332-' + Math.floor(Math.random() * Date.now())
      };
    },
    mounted() {
      this.loadAdScript();
    },
    methods: {
      loadAdScript() {
        const script = document.createElement('script');
        script.async = true;
        script.setAttribute('data-cfasync', 'false');
        script.src = 'https://platform.bidgear.com/pubbidgear-ad.js';
        script.type = 'text/javascript';
        script.onload = () => {
          window.pubbidgeartag = window.pubbidgeartag || [];
          window.pubbidgeartag.push({
            zoneid: 9332,
            id: this.adId,
            wu: window.location.href
          });
        };
        script.onerror = () => {
          console.error('Failed to load the ad script');
        };
        document.head.appendChild(script);
      }
    }
  };
  </script>
  