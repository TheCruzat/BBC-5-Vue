<template>
  <div class="flat">
    <h3>have a question?</h3>
    <p></p>
    <p><a :href="'mailto:dan@thecruzat.com?subject='+subject" class="btn">Ask Me Anything</a></p>
  </div>
</template>

<script>
export default {
  name: "FinaleCTA",
  props: {
    subject: String
  }
}
</script>

<style lang="scss">

</style>
