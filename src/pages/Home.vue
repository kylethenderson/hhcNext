<template>
	<q-page>
		<Hero />
		<About />
		<!-- <Blurb /> -->
		<Services />
		<!-- <Contact /> -->
		<Team />
		<Steps />
		<!-- <Testimonials /> -->
  </q-page>
</template>


<script>
import { defineComponent } from 'vue'
import Hero from "src/components/home/hero.vue";
import About from "src/components/home/about.vue";
// // import Blurb from "src/components/home/blurb";
import Services from "src/components/home/services.vue";
// import Contact from "src/components/home/contact";
import Team from "src/components/home/team.vue";
import Steps from "src/components/home/steps.vue";

export default defineComponent({
  name: 'pages-home',

  components: {
    Hero,
    About,
    Services,
    // Contact,
    Team,
    Steps,
  },

  setup () {
    
    return {
      //
    }
  }
})
</script>

<style scoped>
</style>