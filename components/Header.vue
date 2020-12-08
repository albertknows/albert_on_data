<template>
    <header class="header">
      <nuxt-link to="/" class="logo">a<span class="txt-color">f</span></nuxt-link>
      <input class="menu-btn" type="checkbox" id="menu-btn" v-model="menuChecked"/>
      <label class="menu-icon" for="menu-btn"><span class="navicon"></span></label>
      <li class="mobile-color-mode" @click="colors.push(colors.shift()); $colorMode.preference = colors[0]">
        <a aria-label="Dark Mode">
          <img class="icon-filter" style="color:#fff;" height="16" width="16" src="/icon/dark-mode.svg" alt="Dark Mode"/>
        </a>
      </li>        
      
      <ul class="menu">
        <li><nuxt-link to="/blog/" @click.native="menuChecked=false">blog</nuxt-link></li>
        <li><nuxt-link to="/about/" @click.native="menuChecked=false">about</nuxt-link></li>
        <li class="color-mode" @click="colors.push(colors.shift()); $colorMode.preference = colors[0]">
          <a aria-label="Dark Mode">
            <img class="icon-filter" style="color:#fff;" height="16" width="16" src="/icon/dark-mode.svg" alt="Dark Mode"/>
          </a>
        </li>
      </ul>

    </header>
</template>

<script>
export default {
    props: ['menuChecked'],
    data() {
      return {
        colors: ['light', 'dark'],
      }
    }
}
</script>
