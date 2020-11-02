<template>
  <section>
    <div class="flat">
      <h3>dialects</h3>
      <p>regulars[ HTML, JS, CSS, PHP, Sass, React, Vue, Angular, Next, Nuxt, Gatsby, WP API ];</p>
      <p>priors[ WordPress, JQuery, Bootstrap, Foundation, Flash ];</p>
      <p>extras[ Team Support, QA, Sound Design ];</p>
    </div>

    <div class="flat">
      <h3>agencies + organizations</h3>
      <p>ConnectiveDX, BASIC, EY Design Studio, Hanlon Brown, Razorfish, Babcock & Jenkins, Aquent, Webtrends, Opus Creative, The Brigade, Vitamin T, Mindjet, Periscope, Polymer Studios.</p>
    </div>

    <div class="flat">
      <h3>brands handled</h3>
      <p>PELICAN, Riot Games, ATT, Sitepoint, KFC, MGM Studios, Intel, Nike, Sony, LinkedIn, Corelight, Coca Cola, Rose City Rollers, Microsoft, IBM, Audi, Best Buy, BikePunk, Providence Healthcare, Toshiba, Adidas, VTech, Autodesk, Icon Tires, Qwest, Sterling Communications, Cascade Brewing, the Union Wine Company and Sock It to Me Socks.</p>
    </div>

    <FinaleCTA subject="I want to talk to you about your experience" />
  </section>
</template>

<script>
import FinaleCTA from "@/components/FinaleCTA";
export default {
  name: 'SkillsExp',
  components: {
    FinaleCTA
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
