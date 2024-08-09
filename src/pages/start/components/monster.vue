<template>
  <div class="iframe-container">
    <iframe
      ref="iframe"
      src="https://mg.qiusyan.top/"
      frameborder="0"
      scrolling="auto"
      allowfullscreen
      class="iframe-content"
    ></iframe>
  </div>
  
</template>

<script>
import { IosAirplane } from '@vicons/ionicons4';
import { NAlert, NIcon } from 'naive-ui';
import { useI18n } from 'vue-i18n';
export default {
  mounted() {
    window.addEventListener("resize", this.adjustIframeHeight);
    this.adjustIframeHeight(); 
  },
  beforeDestroy() {
    
    window.removeEventListener("resize", this.adjustIframeHeight);
  },
  methods: {
    adjustIframeHeight() {
      const iframe = this.$refs.iframe;
      if (iframe) {
        iframe.style.height = window.innerHeight + "px";
      }
    },
  },
};
</script>

<style scoped>
.iframe-container {
  width: 86vw;
  height: 100vh;
  overflow: hidden;
}

.commuse {
  width: 500px;
  margin: auto;
}

.commuse-item {
  display: flex;
  align-items: center;
  color: #000;
  margin: 18px 0;

  >div {
    &:nth-child(1) {
      width: 150px;
      text-align: right;
      padding-right: 10px;
      color: #6b6a6a !important;
    }
  }
}

.generate {
  display: flex;
  align-items: center;
  margin-left: 100px;
}
@media screen and (max-width: 768px) {
  .commuse {
    width: 100%; 
    padding: 10px; 
  }

  .commuse-item {
    margin: 18px 0 10px; 
  }

  .commuse-item > div:nth-child(1) {
    width: auto; 
    text-align: left; 
    padding: 0; 
    margin-bottom: 5px; 
  }

  .generate {
    display: block; 
    margin-left: 0; 
    width: 100%; 
    margin-bottom: 80px; 
    margin-top: 10px; 
    text-align: center; 
  }
  .generate > .arco-input {
    margin-bottom: 10px; 
  }
  .generate button { 
    display: block; 
    width: 100%; 
    margin-top: 10px; 
    
  }
}
</style>
