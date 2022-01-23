<template>
  <div class="container" ref="onStart">
    <div class="display">
      <div class="display__line" v-for="(line, index) in lines" v-bind:key="index">
        <span class="display__line__time" key="index"> {{ line.time }} [System]: </span>
        <span class="display__line__text" v-html="line.text"></span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  position: fixed;
  height: 100vh;
  width: 100vw;

  top: 0;
  left: 0;

  overflow: hidden;
  display: flex;

  animation: onStart 500ms linear;
  background-color: $darkBackground;

  .display {
    display: flex;
    flex-direction: column;
    padding: 1em;

    &__line {
      margin-top: 0.5em;
      color: $greenText;
      opacity: 1;
      margin-left: 0;
      width: calc(100vw - 2em);

      animation-delay: 500ms;
      animation: onShowLine 500ms linear;

      &__time {
        font-weight: 900;
      }
    }
  }
}
</style>

<script lang="ts">
import moment from '@nuxtjs/moment'

export default {
  name: 'OnStart',
  data() {
    const linesData: Array<string> = [
      `Start system...`,
      `This page was created by ZB Venom`,
      `Follow my instagram <a href="https://www.instagram.com/zb_venom/">https://www.instagram.com/zb_venom/<a/>`,
      `Go to my GitHub <a href="https://github.com/zb-venom">https://github.com/zb-venom<a/>`,
      `Loading images...`,
      `Loading fonts...`,
      `Loading styles...`,
      `Loading js code...`,
      `Set HASH: 4e78bbf07e9c2299cd3cdbe4aa9e1345a38ff18d1eebef59a6952ac9ee608d68`,
      `Ready ✓`,
      `Ready ✓`,
      `Ready ✓`,
      `Ready ✓`,
      `Welcome to ZB Venom Page`,
    ]
    const lines: Array<object> = []
    return {
      linesData,
      lines,
    }
  },
  methods: {
    async sleep(ms: number): Promise<void> {
      return new Promise((resolve) => setTimeout(resolve, ms))
    },
  },
  async mounted() {
    for (const line of (this as any).linesData) {
      ;(this as any).lines.push({
        text: line,
        time: (this as any).$moment().format('DD.MM.YYYY HH:mm:ss.SSS'),
      })
      await (this as any).sleep(100)
    }
    await (this as any).sleep(1000)
    ;(this as any).$refs.onStart.animate(
      [{ opacity: 1 }, { opacity: 0, top: '-100%', bottom: '100%' }],
      {
        duration: 500,
        easing: 'linear',
        fill: 'forwards',
      }
    )
    await (this as any).sleep(500)
    ;(this as any).$refs.onStart.style.display = 'none'
  },
}
</script>
