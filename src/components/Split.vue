<template>
  <section :style="style">
    <h2 v-if="msg" v-html="msg"></h2>
  </section>
</template>

<script>
export default {
  name: "Split",
  props: {
    msg: String,
    img: String,
  },
  computed: {
    style () {
      return 'background: url('+this.img+') 50% 80% no-repeat; background-size: cover;';
    }
  },
}
</script>

<style scoped lang="scss">
  section {
    width: 100%; // 88vw; // calc(100% - 40px);
    // opacity: 0.8;
    min-height: 50vh;
    margin-left: auto;
    margin-right: auto;

    margin: calc(8vh) auto 8vh;
    justify-content: flex-end;
    position: relative;
    &:after {
      display: block;
      content: "";
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.5);
      z-index: 0;
    }

    h2 {
      color: #fff;
      text-shadow: 0 0 2px var(--bod);
      margin-bottom: var(--gutter);
      position: relative;
      z-index: 1;

      @include mFlip() {
        margin-bottom: 0;
      }
    }

    @include mFlip() {
      width: 88vw;
      min-height: 30vh;
      justify-content: center;

      margin: 24vh auto 0; // 8vh;
    }
  }
</style>
