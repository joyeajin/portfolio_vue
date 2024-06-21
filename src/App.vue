<template>
  <!-- <div class="">dd</div> -->
  <SkipSection />
  <HeaderSection />
  <main id="main" role="main">
    <IntroSection />
    <SkillSection />
    <SiteSection />
    <PortSection />
    <ContactSection />
  </main>
  <FooterSection />
</template>

<script>
import HeaderSection from "@/components/HeaderSection.vue";
import FooterSection from "@/components/FooterSection.vue";
import IntroSection from "@/components/IntroSection.vue";
import SkillSection from "@/components/SkillSection.vue";
import SiteSection from "@/components/SiteSection.vue";
import PortSection from "@/components/PortSection.vue";
import ContactSection from "@/components/ContactSection.vue";
import SkipSection from "@/components/SkipSection.vue";
import Lenis from "@studio-freight/lenis";

export default {
  name: "App",
  components: {
    SkipSection,
    HeaderSection,
    FooterSection,
    IntroSection,
    SkillSection,
    SiteSection,
    PortSection,
    ContactSection,
  },
  mounted() {
    this.scrollAnimation();
  },
  methods: {
    scrollAnimation() {
      const lenis = new Lenis({
        duration: 1,
        easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
        direction: "vertical",
        gestureDirection: "vertical",
        smooth: true,
      });

      function raf(time) {
        lenis.raf(time);
        requestAnimationFrame(raf);
      }

      requestAnimationFrame(raf);

      lenis.on("scroll", (e) => {
        console.log(e);
      });
    },
  },
};
</script>

<style></style>
