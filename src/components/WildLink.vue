<template>
  <a class="wildlink" :href="url" :title="title" target="_blank">
    <p>{{ title }}</p>
    <p>{{ desc }}</p>
  </a>
</template>

<script>
export default {
  name: 'WildLink',
  props: {
    title: String,
    url: String,
    desc: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  a.wildlink {
    color: var(--bod);
    text-decoration: none;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: center;
    background: $paper;
    border: 1px solid var(--paper);
    padding: 4px;
    text-align: center;

    width: 100%;
    margin-bottom: 1.8rem;
    transition: all 0.35s ease-in;

    @include mFlip() {
      width: calc(50% - 0.9rem);
    }

    &:hover {
      transition: all 0.15s ease-out;
      background: lighten($paper, 4%);
      border-color: darken($paper, 4%);

      p:first-child {
        color: var(--hot);

        + p {
          color: var(--bod);
        }
      }
    }

    p {
      margin: 0;
      display: inline-block;
      width: auto;
      transition: all 0.2s;


      &:first-child {
        // color: var(--hot);
        border-bottom: 1px solid #ccc;
        margin-bottom: 0.2rem;
      }

      + p {
        font-size: 60%;
        border: none;
        opacity: 0.8;
        color: #999;
      }
    }
  }
</style>
