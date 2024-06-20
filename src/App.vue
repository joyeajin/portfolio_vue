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
};
</script>

<style></style>
