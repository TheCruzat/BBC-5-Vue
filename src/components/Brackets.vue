<template>
  <div class="brackets">
    <strong>{</strong>
    <strong>}</strong>
  </div>
</template>

<script>
export default {
  name: "Brackets"
}
</script>

<style scoped lang="scss">

  .brackets {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    display: none;
    align-items: center;
    justify-content: space-between;
    z-index:-2;
    color: var(--paper); // lighten($paper, 2%);

    @include mFlip() {
      display: flex;
    }
  }

  strong {
    // font-size: 30rem;
    font-size: 32vw;
    font-weight: 100;
    margin-left: -3.2vw;

    + strong {
      margin-left: 0;
      margin-right: -3.2vw;
    }
  }

</style>
