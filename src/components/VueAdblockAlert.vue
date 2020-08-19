<template>
    <div class="adblock-dialog" v-if="getAdBlockEnabled">
      <div class="adblock-border-5 q-card w-100">
        <h2 class="" v-text="getTitle"></h2>
        <h3 class=""  v-text="subtitle"></h3>

        <p class="" v-text="text"></p>
        <div class="">
            <!--q-video :ratio="16/9" :src="video" /-->
        </div>
      </div>
    </div>
</template>
<script>

export default {
    name: 'VueAdblockAlert',
    props: {
        title: {
            type: String
        },
        subtitle: {
            type: String
        },
        text: {
            type: String
        },
        borderColor: {
          type: String
        },
        textColor: {
          type: String
        },
        bgColor: {
          type: String
        }
    },
    data() {
        return {
          adBlockEnabled: false,
        }
    },
    mounted() {
      let root = document.documentElement;
      if(this.borderColor) root.style.setProperty('--adblock-border-color', this.borderColor);
      if(this.textColor) root.style.setProperty('--adblock-text-color', this.textColor);
      if(this.bgColor) root.style.setProperty('--adblock-bg-color', this.bgColor);
      this.checkAdBlockIsEnabled()
    },
    methods: {
      checkAdBlockIsEnabled() {
        const ad = document.createElement('div')
        ad.innerHTML = '&nbsp;'
        ad.className = 'adsbox'
        document.body.appendChild(ad)
        if (ad.offsetHeight === 0) {
          document.body.classList.add('ad-block-detect')
          this.adBlockEnabled = true;
        }
        ad.remove()
      }
    },
    computed: {
      getAdBlockEnabled() {
        return this.adBlockEnabled
      },
      getTitle() {
        return this.title
      }
    }
}
</script>
<style>

  :root {
    --adblock-border-color: #d4145a;
    --adblock-bg-color: #ffffff;
    --adblock-text-color: #000000;
  }

  body.ad-block-detect {
    overflow-y: hidden;
  }

  .adblock-dialog {
    border: 2px solid var(--adblock-border-color);
    border-radius: 5px;
    background: var(--adblock-bg-color);
    color: var(--adblock-text-color);
    width: 100%;
    height: 100%;
    padding: 15px;
  }
</style>
