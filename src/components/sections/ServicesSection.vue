<script setup>
import ServiceItem from "./section-components/ServiceItem.vue";
import MainHeading from "./section-components/MainHeading.vue";
</script>

<template>
  <section class="services" id="services">
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
    <section class="desgin" id="desgin">
      <div class="images">
        <img src="../../assets/images/black-phone.png" alt="" />
        <img src="../../assets/images/white-phone.png" alt="" />
      </div>
      <div class="text">
        <h3 v-text="serviceFeature.title"></h3>
        <ul>
          <li
            v-for="(feature, index) in serviceFeature.features"
            :key="index"
            :style="'--icon: ' + feature.iconCode + ';'"
            v-text="feature.text"
          ></li>
        </ul>
      </div>
    </section>
  </section>
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
      serviceFeature: {
        title: "OUR DESIGNS COMES WITH...",
        features: [
          { text: "Responsive Design", iconCode: "'\\f108'" },
          { text: "Modern And Clean Design", iconCode: "'\\f108'" },
          { text: "Clean Code", iconCode: "'\\f108'" },
          { text: "Browser Friendly", iconCode: "'\\f108'" },
        ],
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
