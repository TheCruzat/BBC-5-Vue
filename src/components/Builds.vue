<template>
  <section>

    <div v-for="set in links" :key="set.header" class="flat">
      <h3>{{ set.header }}</h3>
      <WildSet>
        <WildLink v-for="link in set.links" :key="link.title" :title="link.title" :desc="link.desc" :url="link.url"  />
      </WildSet>
    </div>

    <FinaleCTA subject="I want to talk about one of your builds" />

  </section>
</template>

<script>
import WildSet from "@/components/WildSet";
import WildLink from "@/components/WildLink";
import FinaleCTA from "@/components/FinaleCTA";
import {LinkSets} from "@/content/LinkSets";
export default {
  name: 'Builds',
  components: {WildSet, WildLink, FinaleCTA},
  data:function() {
    return {
      links: LinkSets
    }
  },
  props: {
    msg: String
  }
}
</script>

<style>

</style>
