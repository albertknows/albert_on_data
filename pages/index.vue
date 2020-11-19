<template>
  <div>
    <div id="particles-js"></div>
    <div class="home-container" >
      <div class="u-full-width">
        <h1 class="site-title">
            albert<span class="txt-color"> </span>farrales
        </h1>
        <h5 class="subtitle" id="type-it-text">
          <!-- Fancy Typed Text -->
        </h5>
        <p>
          because Instagram and Twitter were too basic / aspiring business analyst
        </p>
        <span class="sm-txt"><em>I wouldn't read too much into anything here...</em></span>

        <div class="m20">
          <ColorModePicker />
        </div>
      </div>
      <script async src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
    </div>
</div>
</template>

<script>
import TypeIt from 'typeit'
import ColorModePicker from '@/components/ColorModePicker'

// Only import particles.js on client side
if (process.browser) {
  require('particles.js')
}

export default {
  components: {
    ColorModePicker
  },
  head() {
    return {
      title: 'albert farrales - a data science blog',
      meta: [
      { hid: 'description',
      name: 'description',
      content: 'A personal data science blog meant to discuss the field at a high level.' },
      {
          'property':  'og:url',
          'content':  `https://alberfarrales.com/`,
      },
      {
          'property':  'og:title',
          'content':  `albertfarrales - a data science blog`,
      },
      {
          'property':  'og:type',
          'content':  `website`,
      },
      {
          'property':  'og:description',
          'content': `A personal data science blog meant to discuss the field at a high level.`.replace(/<\/?[^>]+(>|$)/g, ""),
      },
      {
          'property':  'og:image',
          'content': `https://gregondata.com/favicon/apple-touch-icon.png`
      }
      ]
    };
  },
  methods: {
    initParticles() {
      window.particlesJS.load('particles-js', '/particles.json', function() {
        // If need to do anything once config is loaded
    });
    }
  },
  mounted() {
    this.initParticles()

    new TypeIt("#type-it-text")
    .type("do you wish to continue?", {speed: 60, delay: 200})
    .delete(30, {delay: 200})
    .type("access granted", {speed: 60})
    .break({delay: 300})
    .type("can i interest you in...", {speed: 60})
    .break({delay: 100})
    .type("<a href='/blog/'>some posts</a>", {speed: 60})
    .break({delay: 200})
    .type("or maybe", {speed: 60})
    .break({delay: 200})
    .type("<a href='/projects/'>some projects of mine</a>", {speed: 60})
    .go();

    console.log("hey you, stop it.")
    console.log("110 111 32 114 101 97 108 108 121 44 32 115 116 111 112 32 105 116 46")

    

  }

  
}
</script>
