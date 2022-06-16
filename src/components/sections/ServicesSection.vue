<script setup>
import ServiceItem from "./section-components/ServiceItem.vue";
import MainHeading from "./section-components/MainHeading.vue";
import DesginFeatures from "./DesginFeatures.vue";
</script>

<template>
  <section :class="heading.title" :id="heading.title">
    <div class="container">
      <MainHeading>
        <template #title>{{ heading.title }}</template>
        <template #text>{{ heading.text }}</template>
      </MainHeading>
      <div class="serv-container">
        <ServiceItem v-for="(service, index) in services" :key="index">
          <template #icon><i :class="service.icon"></i></template>
          <template #serv-title>{{ service.title }}</template>
          <template #serv-text>{{ service.text }}</template>
        </ServiceItem>
      </div>
    </div>
  </section>
  <DesginFeatures />
</template>

<script>
export default {
  data() {
    return {
      heading: {
        title: "services",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
      services: [
        {
          id: 0,
          icon: "fa-solid fa-desktop fa-4x",
          title: "Vorem amet intuitive",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
              Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a.
              Curabitur aliquet quam.`,
        },
        {
          id: 1,
          icon: "fa-solid fa-cog fa-4x",
          title: "Vorem amet intuitive",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
              Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a.
              Curabitur aliquet quam.`,
        },
        {
          id: 2,
          icon: "fa-solid fa-pen-ruler fa-4x",
          title: "Vorem amet intuitive",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
              Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a.
              Curabitur aliquet quam.`,
        },
        {
          id: 3,
          icon: "fa-solid fa-camera fa-4x",
          title: "Vorem amet intuitive",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
              Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a.
              Curabitur aliquet quam.`,
        },
      ],
    };
  },
};
</script>
