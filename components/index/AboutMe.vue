<template>
  <div class="container">
    <div class="box">
      <div class="block left" ref="left">
        <span class="label">HTML+SCSS code of this page</span>
        <div class="display" ref="display1">
          <div class="text" v-html="code"></div>
        </div>
        <div class="left__logo">V</div>
      </div>
    </div>
    <div class="box">
      <div class="block right" ref="right">
        <span class="label">JS code of this page</span>
        <div class="display" ref="display2">
          <div class="text" v-html="code"></div>
        </div>
        <div class="right__logo"></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  position: fixed;
  inset: 0;
  top: 100px;
  display: grid;
  grid-template-columns: 1fr 1fr;

  .box {
    position: relative;
    width: 100%;
    height: 100%;

    .block {
      position: absolute;
      background-color: $blockBackground;
      width: 100%;
      height: 100%;

      padding: 30px;
      padding-top: 50px;
      box-sizing: border-box;

      display: flex;
      justify-content: center;
      align-items: center;

      span.label {
        position: absolute;
        padding: 10px 20px;
        color: $linkColor;
        background-color: $blockBackground;
        border: 10px solid black;
        border-radius: 25px;
        font-weight: 900;
        top: 20px;
        left: 60px;
        z-index: 3;
      }

      .display {
        position: relative;
        width: 100%;
        height: 100%;
        background-color: $consoleBackground;
        border: 10px solid $darkBackground;
        border-radius: 5px;
        box-sizing: border-box;
        padding: 5px 10px;
        overflow: hidden;
        box-shadow: 0 0 10px black;
        z-index: 1;

        .text {
          color: $greenText;
        }
      }

      &.left {
        margin-left: -120%;
        border-right: 5px solid $blockBorderColor;
        z-index: 2;

        .left__logo {
          position: absolute;
          height: 100px;
          width: 140px;
          right: -85px;
          top: 50%;
          transform: translate(0, -50%);
          z-index: 2;

          color: $linkColor;

          display: flex;
          justify-content: center;
          align-items: center;
          font-family: 'Saira Stencil One', cursive;

          background: $bodyBackground;
          border: 10px solid $blockBorderColor;
          border-radius: 10px;
          font-size: 70px;
        }
      }

      &.right {
        margin-left: 100%;
        border-left: 5px solid $blockBorderColor;
        z-index: 1;

        .right__logo {
          position: absolute;
          height: 110px;
          width: 75px;
          left: -5px;
          top: 50%;
          transform: translate(0, -50%);

          display: flex;
          justify-content: center;
          align-items: center;
          font-family: 'Saira Stencil One', cursive;

          background: $bodyBackground;
          border: 5px solid $blockBorderColor;
          border-radius: 10px;
          border-left: none;
          font-size: 50px;
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
    return {
      code: `&lt;template&gt;</br>&emsp;&lt;div class="container"&gt;</br>&emsp;&emsp;&lt;div class="box"&gt;</br>&emsp;&emsp;&emsp;&lt;div class="block left" ref="left"&gt;</br>&emsp;&emsp;&emsp;&emsp;&lt;div class="left__logo"&gt;V&lt;/div&gt;</br>&emsp;&emsp;&emsp;&emsp;&lt;div class="text"&gt;{{ code }}&lt;/div&gt;</br>&emsp;&emsp;&emsp;&lt;/div&gt;</br>&emsp;&emsp;&lt;/div&gt;</br>&emsp;&emsp;&lt;div class="box"&gt;</br>&emsp;&emsp;&emsp;&lt;div class="block right" ref="right"&gt;</br>&emsp;&emsp;&emsp;&emsp;&lt;div class="right__logo"&gt;&lt;/div&gt;</br>&emsp;&emsp;&emsp;&emsp;&lt;div class="text"&gt;{{ code }}&lt;/div&gt;</br>&emsp;&emsp;&emsp;&lt;/div&gt;</br>&emsp;&emsp;&lt;/div&gt;</br>&emsp;&lt;/div&gt;</br>&lt;/template&gt;</br></br>&lt;style lang="scss" scoped&gt;</br>.container {</br>&emsp;position: fixed;</br>&emsp;inset: 0;</br>&emsp;top: 100px;</br>&emsp;display: grid;</br>&emsp;grid-template-columns: 1fr 1fr;</br></br>&emsp;.box {</br>&emsp;&emsp;position: relative;</br>&emsp;&emsp;width: 100%;</br>&emsp;&emsp;height: 100%;</br></br>&emsp;&emsp;.block {</br>&emsp;&emsp;&emsp;position: absolute;</br>&emsp;&emsp;&emsp;background-color: $blockBackground;</br>&emsp;&emsp;&emsp;width: 100%;</br>&emsp;&emsp;&emsp;height: 100%;</br></br>&emsp;&emsp;&emsp;padding: 30px;</br>&emsp;&emsp;&emsp;box-sizing: border-box;</br></br>&emsp;&emsp;&emsp;&.left {</br>&emsp;&emsp;&emsp;&emsp;margin-left: -100%;</br>&emsp;&emsp;&emsp;&emsp;border-right: 5px solid $blockBorderColor;</br>&emsp;&emsp;&emsp;&emsp;z-index: 2;</br></br>&emsp;&emsp;&emsp;&emsp;.left__logo {</br>&emsp;&emsp;&emsp;&emsp;&emsp;position: absolute;</br>&emsp;&emsp;&emsp;&emsp;&emsp;height: 100px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;width: 140px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;right: -85px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;top: 50%;</br>&emsp;&emsp;&emsp;&emsp;&emsp;transform: translate(0, -50%);</br></br>&emsp;&emsp;&emsp;&emsp;&emsp;color: $linkColor;</br></br>&emsp;&emsp;&emsp;&emsp;&emsp;display: flex;</br>&emsp;&emsp;&emsp;&emsp;&emsp;justify-content: center;</br>&emsp;&emsp;&emsp;&emsp;&emsp;align-items: center;</br>&emsp;&emsp;&emsp;&emsp;&emsp;font-family: 'Saira Stencil One', cursive;</br></br>&emsp;&emsp;&emsp;&emsp;&emsp;background: $bodyBackground;</br>&emsp;&emsp;&emsp;&emsp;&emsp;border: 10px solid $blockBorderColor;</br>&emsp;&emsp;&emsp;&emsp;&emsp;font-size: 70px;</br>&emsp;&emsp;&emsp;&emsp;}</br>&emsp;&emsp;&emsp;}</br></br>&emsp;&emsp;&emsp;&.right {</br>&emsp;&emsp;&emsp;&emsp;margin-left: 100%;</br>&emsp;&emsp;&emsp;&emsp;border-left: 5px solid $blockBorderColor;</br>&emsp;&emsp;&emsp;&emsp;z-index: 1;</br></br>&emsp;&emsp;&emsp;&emsp;.right__logo {</br>&emsp;&emsp;&emsp;&emsp;&emsp;position: absolute;</br>&emsp;&emsp;&emsp;&emsp;&emsp;height: 110px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;width: 75px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;left: -5px;</br>&emsp;&emsp;&emsp;&emsp;&emsp;top: 50%;</br>&emsp;&emsp;&emsp;&emsp;&emsp;transform: translate(0, -50%);</br></br>&emsp;&emsp;&emsp;&emsp;&emsp;display: flex;</br>&emsp;&emsp;&emsp;&emsp;&emsp;justify-content: center;</br>&emsp;&emsp;&emsp;&emsp;&emsp;align-items: center;</br>&emsp;&emsp;&emsp;&emsp;&emsp;font-family: 'Saira Stencil One', cursive;</br></br>&emsp;&emsp;&emsp;&emsp;&emsp;background: $bodyBackground;</br>&emsp;&emsp;&emsp;&emsp;&emsp;border: 5px solid $blockBorderColor;</br>&emsp;&emsp;&emsp;&emsp;&emsp;border-left: none;</br>&emsp;&emsp;&emsp;&emsp;&emsp;font-size: 50px;</br>&emsp;&emsp;&emsp;&emsp;}</br>&emsp;&emsp;&emsp;}</br>&emsp;&emsp;}</br>&emsp;}</br>}`,
    }
  },
  async mounted() {
    const right: HTMLElement = (this as any).$refs.right
    const left: HTMLElement = (this as any).$refs.left
    const display1: HTMLElement = (this as any).$refs.display1
    const display2: HTMLElement = (this as any).$refs.display2
    let displayTop1 = Math.floor(Math.random() * 50),
      displayTop2 = Math.floor(Math.random() * 80 + 200)
    left.animate([{ marginLeft: '-120%' }, { marginLeft: '0' }], {
      duration: 300,
      easing: 'ease-in',
      fill: 'forwards',
      delay: 3000,
    })
    right.animate([{ marginLeft: '100%' }, { marginLeft: '0' }], {
      duration: 300,
      easing: 'ease-in',
      fill: 'forwards',
      delay: 3000,
    })
    left.animate([{ marginLeft: '-100%' }, { marginLeft: '0' }], {
      duration: 300,
      easing: 'ease-in',
      fill: 'forwards',
      delay: 3000,
    })
    ;(this as any).displayIntreval = setInterval(() => {
      display1.scrollTop = displayTop1
      display2.scrollTop = displayTop2
      displayTop1 +=
        displayTop1 >= display1.scrollHeight - left.scrollHeight * 0.8
          ? -displayTop1
          : 2
      displayTop2 +=
        displayTop2 >= display2.scrollHeight - left.scrollHeight * 0.8
          ? -displayTop1
          : 2
    }, 100)
  },
  destroyed() {},
})
</script>
