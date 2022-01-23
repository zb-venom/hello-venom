<template>
  <div class="container">
    <nav ref="Nav">
      <div class="logo">V</div>
      <div class="links">
        <div class="link">About Me</div>
        <div class="link">Codes</div>
        <div class="link">Funy</div>
      </div>
      <div class="social"></div>
    </nav>
  </div>
</template>

<style lang="scss" scoped>
.container {
  position: relative;
  height: 100px;
  width: 100vw;

  background-color: $navBackground;

  nav {
    display: flex;
    justify-content: space-around;
    height: 100%;
    margin-top: -120px;
    border-bottom: 5px solid $navBorderColor;
    box-shadow: 0 0 10px black;

    .logo {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100px;
      height: 100%;
      color: white;
      font-size: 70px;
      background-color: $navBackgroundLigth;
      font-family: 'Saira Stencil One', cursive;
      user-select: none;
      border-radius: 10px 10px 0 0;
      cursor: pointer;
      text-shadow: 0 0 5px white, 0 0 70px white;

      transition: all 300ms;

      &:hover {
        color: $greenText;
        animation: logoShadow 5s linear infinite;
      }

      &::after {
        content: '';
        position: absolute;
        top: 100px;
        height: 5px;
        width: 100%;
        background-color: $navBackgroundLigth;
        border-bottom: 10px solid white;
        border-radius: 0 0 30px 30px;
        box-shadow: 0 0 10px black;
      }

      &::before {
        content: '';
        position: absolute;
        height: 100px;
        width: 100%;
        background-color: transparent;
        box-shadow: 0 0 10px black;
        border-radius: 10px 10px 0 0;
      }
    }

    .links {
      display: flex;
      align-items: center;
      cursor: pointer;

      font-size: 20px;
      font-weight: 700;
      color: $linkColor;

      .link {
        margin: 20px;

        &:hover {
          color: $activeLinkColor;
          text-shadow: 0px 0px 10px $activeLinkColor,
            0px 0px 40px $activeLinkColor, 0px 0px 70px $activeLinkColor;
        }
      }
    }
  }
}
</style>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'NavBar',
  data() {
    return {}
  },
  async mounted() {
    const nav: HTMLElement = (this as any).$refs.Nav
    nav.animate([{ marginTop: '-100px' }, { marginTop: '0' }], {
      duration: 500,
      easing: 'ease-in',
      fill: 'forwards',
      delay: 3000,
    })
  },
})
</script>
