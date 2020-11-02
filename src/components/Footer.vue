<template>
  <footer>
    <Goodies :type="GoodieTypes.footer" />
    <Logo :type="LogoTypes.footer" />
    <div class="read"><h3>builtby the cruzat</h3>copyright &copy;2008-{{ yr }}<span> : </span><em><br></em>all rights reserved<span> : </span><em><br></em>please wash your hands</div>
    <div :style="{background: 'url('+bg+') 50% 100% no-repeat scroll', backgroundSize: 'cover'}" />
  </footer>
</template>

<script>
import Logo, {types as LogoTypes} from "@/components/Logo";
import Goodies, {types as GoodieTypes} from "@/components/Goodies";
import bg from '@/assets/bg-board.jpg';
const now = new Date();
const yr = now.getFullYear();
export default {
  name: 'Footer',
  components: {
    Logo,
    Goodies,
  },
  props: {
    msg: String
  },
  data:function() {
    return {
      LogoTypes: LogoTypes,
      GoodieTypes: GoodieTypes,
      yr: yr,
      bg: bg,
    }
  }
}
</script>

<style scoped lang="scss">
  footer {
    background: #000;
    min-height: 90vh;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    overflow: hidden;

    h3 {
      color: var(--hot);
    }

    svg {
      margin-bottom: 8.4rem;
      align-self: flex-start;
      @include mFlip() {
        max-width: 50vw;
        align-self: center;
        margin-bottom: 4.8rem;
        width: auto;
      }
    }

    @media (max-width: 64rem) {
      text-align: left;
      span {
        display: none;
      }
    }

    @include mFlip() {
      br:not(.keep) {
        display: none;
      }
    }

    .read, svg, .goodies-set {
      position: relative;
      z-index: 2;
    }

    .goodies-set {

      @include mFlip() {
        align-self: center;
      }
    }

    .read {
      padding: 20px;
      color: var(--paper);
      position: absolute;
      bottom: 0; left: 0; right: 0;
      // background: var(--paper);
      //box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
      // border-top: 1px solid #e0e0e0;

      +div {
        opacity: 0.2;
        position: absolute;
        z-index: 0;
        top: 0; left: 0; right: 0; bottom: 0;
        // background: url("https://miro.medium.com/max/6000/1*xBAAzp2dbEan-3sRgVT6yw.jpeg") center center no-repeat fixed;
        // background-size: cover;
      }
    }
  }
</style>
