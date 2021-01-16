<template>
  <div>
    <div id="particles-js"></div>
    <div class="home-container" >
      <div class="u-full-width">
        <h1 class="site-title">
            albert<span class="txt-color"> farrales</span>
        </h1>
        <h5 class="subtitle" id="type-it-text">
          <!-- Fancy Typed Text -->
        </h5>
        <p>
           
        </p>
        <span class="sm-txt"><em></em></span>

        <div class="m20">
        </p>
          <ColorModePicker />
        </div>
      </div>
      </p>
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
      title: 'albert farrales - story of my life',
      meta: [
      { hid: 'description',
      name: 'description',
      content: 'just a regular website on the internet.' },
      {
          'property':  'og:url',
          'content':  `https://albertfarrales.com/`,
      },
      {
          'property':  'og:title',
          'content':  `albert farrales - story of my life`,
      },
      {
          'property':  'og:type',
          'content':  `website`,
      },
      {
          'property':  'og:description',
          'content': `just a regular website on the internet.`.replace(/<\/?[^>]+(>|$)/g, ""),
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
    .type("do you wish to continue?", {speed: 70, delay: 150})
    .delete(25, {delay: 250})
    .type("access granted", {speed: 70, delay: 120})
    .delete(15, {delay: 250})
    .type("welcome to my personal website", {speed: 60, delay: 90})
    .break({delay: 300})
    .type("can i interest you in...", {speed: 60})
    .break({delay: 100})
    .type("<a href='/blog/'>some interesting takes</a>", {speed: 70})
    .break({delay: 50})
    .type("or maybe", {speed: 60})
    .break({delay: 50})
    .type("<a href='/about/'>just a quick introduction</a>", {speed: 70})
    .go();

    console.log("hey you, stop it.")
    console.log("110 111 32 114 101 97 108 108 121 44 32 115 116 111 112 32 105 116 46")

    

  }

  
}
</script>
