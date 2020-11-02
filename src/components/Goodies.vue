<template>
  <div :type="type" class="goodies-set">
    <a v-for="link in links" :key="link.title" :href="link.url" :title="link.title" :data-mega="link.mega" target="_blank">
      <i :class="'fa '+link.icon" />
      <label v-html="link.label"></label>
    </a>
  </div>
</template>

<script>

import { GoodiesLinks } from "@/content/LinkSets";

export const types = {
  header: "header",
  footer: "footer",
}
export default {
  name: "Goodies",
  props: {
    type: types
  },
  data: function() {
    return {
      links: GoodiesLinks
    }
  }
}
</script>

<style scoped lang="scss">
  .goodies-set {
    font-size: 1.8rem;
    display: flex;
    flex-wrap: wrap;
    padding: var(--gutter);
    align-self: flex-start;
    justify-content: space-between;
    width: 100%;

    @include mFlip() {
      font-size: 2.4rem;
      justify-content: space-around;
      padding-left: 0;
      max-width: 720px;
      margin-left: auto;
      margin-right: auto;
    }

    &[type="footer"] {
      margin: 9vh auto 9vh;
      @include mFlip() {
        margin-bottom: 12vh;
      }
      a {
        color: #fff;
        background: #000;
        opacity: 0.6;
        border: 1px solid #222;
        transition: all 0.2s;
        &:hover {
          border-color: #2f2f2f;
          opacity: 1;
        }
      }
    }
  }
  a {
    color: var(--bod);
    display: flex;
    width: calc(50% - var(--gutter)/2); // 100%;
    align-items: center;
    height: 4rem;
    background: var(--paper);
    margin-bottom: var(--gutter);
    padding-left: var(--gutter);

    &[data-mega="true"] {
      @include mFlip() {
        // border: 1px solid #ccc;
        // width: 50%;
        // flex-basis: 2;
      }
    }

    i {
      width: 30px;
      text-align: center;

      @include mFlip() {
        width: 50px;
      }
    }

    label {
      font-size: 1.2rem;
      margin-left: 1rem;
      cursor: pointer;
      @include mFlip() {
        font-size: 1.6rem;
      }
    }

    transition: all 0.35s ease-in;
    &:hover {
      transition: all 0.15s ease-out;
      color: #fff; // var(--hot);
      background: var(--hot);
    }
    + a {
      // margin-top: 1rem;
    }
    @include mFlip() {
      width: calc(33.333% - var(--gutter)); // 100%;
    }
  }
</style>
