<script setup>
import MainHeading from "./section-components/MainHeading.vue";
import StatisticsSection from "./sub-section/about/StatisticsSection.vue";
import SkillsSection from "./sub-section/about/SkillsSection.vue";
import QuoteSection from "./sub-section/about/QuoteSection.vue";
</script>

<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <MainHeading>
        <template #title>{{ heading.title }}</template>
        <template #text>{{ heading.text }}</template>
      </MainHeading>
      <img src="../../assets/images/screens.png" alt="" />
    </div>
  </section>
  <StatisticsSection />
  <SkillsSection />
  <QuoteSection />
</template>

<script>
export default {
  data() {
    return {
      heading: {
        name: "about",
        title: "about us",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
    };
  },
};
</script>
