<template>
  <header>
    <h1><span>Built By The Cruzat</span>

      <Logo :type="types.header" />

    </h1>
    <div class="tiptop"><div class="subset">
      <p class="name">Dan Cruzat</p>
      <p>front end engineer <br>based in portland or</p>
    </div></div>
    <Button><i class="fa fa-chevron-down"></i></Button>
  </header>
</template>

<script>
import Logo, {types} from "@/components/Logo";
export default {
  name: 'Header',
  components: {
    Logo
  },
  data: function() {
    return {
      types: types,
    }
  },
  props: {
    msg: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  header {
    display: flex;
    justify-content: flex-start;
    align-items: center; // flex-start;
    flex-direction: column-reverse;
    background: var(--paper); // #fff;
    height: 90vh;
    padding: 0; // 20px 0;
    position: relative;
    margin-bottom: 10vh;
    @include mFlip() {
      //overflow: visible;
      // flex-direction: column;
      // justify-content: space-between;
    }
  }
  h1, p {
    margin: 0;
  }
  h1 {
    position: relative;
    display: block;
    width: 100%;
    @include mFlip() {
      margin-bottom: -0.8rem;
      width: auto;
    }
    span {
      display: none;
    }
    svg {
      display: block;
      height: auto;
      width: 100%;
      margin: 0 auto -0.9rem;
      @include mFlip() {
        position: relative;
        transform: rotate(0);
        max-width: 100vw;
        width: 70vw;
        margin-top: 0;
        margin-bottom: -1.4rem;
      }
    }
  }
  .tiptop {
    width: 100%;
  }
  .subset {
    width: 100%;
    max-width: 45rem;
    padding-left: var(--gutter);
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 8vh;
    font-family: var(--title);

    @include mFlip() {
      position: relative;
    }
  }
  p {
    text-transform: lowercase;
    font-size: 1.4rem;
    margin: 0;
    padding: 0;
    opacity: 0.4;
    color: var(--bod);
    line-height: 1.2;
    align-self: flex-end;
    text-align: left;
    @include mFlip() {
      width: auto;
      font-size: 2.2vw;
      text-align: left;
      br {
        display: none;
      }
    }

    &.name {
      opacity: 1;
      text-transform: capitalize;
      font-size: 3rem;
      color: var(--hot);
      @include mFlip() {
        font-size: 4vw;
      }
    }
  }

  button {
    background: transparent;
    border: none;
    outline: none;
    position: absolute;
    left: calc(50% - 60px);
    font-size: 2rem;
    color: var(--hot);
    animation: float 1s ease-out infinite;
    width: 120px;
  }
  $chrv: 0.8rem;
  @keyframes float {
    from {
      bottom: -2.5vh;
      opacity: 100;
      font-size: $chrv;
    }
    to {
      bottom: -7.5vh;
      opacity: 0;
      font-size: $chrv*4;
    }
  }
</style>
