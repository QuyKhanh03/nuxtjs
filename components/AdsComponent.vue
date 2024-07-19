<template>
  <div :id="adId"></div>
</template>

<script>
export default {
  data() {
    return {
      adId: 'bg-ssp-9295-' + Math.floor(Math.random() * Date.now())
    };
  },
  mounted() {
    this.loadAd();
  },
  methods: {
    loadAd() {
      const oldScript = document.querySelector('script[src="https://platform.bidgear.com/pubbidgear-ad.js"]');
      if (oldScript) {
        oldScript.remove();
      }

      const script = document.createElement('script');
      script.src = 'https://platform.bidgear.com/pubbidgear-ad.js';
      script.async = true;
      script.setAttribute('data-cfasync', 'false');
      document.body.appendChild(script);

      script.onload = () => {
        window.pubbidgeartag = window.pubbidgeartag || [];
        window.pubbidgeartag.push({
          zoneid: 9295,
          id: this.adId,
          wu: window.location.href
        });
      };
    }
  },
  watch: {
    '$route'() {
      this.adId = 'bg-ssp-9295-' + Math.floor(Math.random() * Date.now());
      this.loadAd();
    }
  }
};
</script>
