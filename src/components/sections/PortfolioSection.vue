<script setup>
import MainHeading from "./section-components/MainHeading.vue";
import ImagesGallery from "./section-components/ImagesGallery.vue";
import VideoSection from "./sub-section/portfolio/VideoSection.vue";
const getImageUrl = (name) => {
  return new URL(`../../assets/images/${name}`, import.meta.url).href;
};
</script>

<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <MainHeading>
        <template #title>{{ heading.title }}</template>
        <template #text>{{ heading.text }}</template>
      </MainHeading>
      <ul class="shuffle">
        <li
          v-for="(shuffle, index) in shuffles"
          :key="index"
          :class="{ active: shuffle.isActive }"
          @click="toggleActive(index)"
          v-text="shuffle.text"
        ></li>
      </ul>
    </div>
    <div class="images-container">
      <ImagesGallery v-for="(work, index) in worksSelected" :key="index">
        <img :src="getImageUrl(work.imgName)" alt="our work" />
        <template #work-title>{{ work.title }}</template>
        <template #work-category>{{ work.category }}</template>
      </ImagesGallery>
    </div>
    <a href="#" class="more">More</a>
    <VideoSection />
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: {
        name: "portfolio",
        title: "portfolio",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
      shuffles: [
        { text: "All", isActive: true },
        { text: "App", isActive: false },
        { text: "Photography", isActive: false },
        { text: "Web", isActive: false },
        { text: "Print", isActive: false },
      ],
      works: [
        {
          imgName: "work-01.jpg",
          title: "Awesome Image",
          category: "App",
        },
        {
          imgName: "work-02.jpg",
          title: "Awesome Image",
          category: "Photography",
        },
        {
          imgName: "work-03.jpg",
          title: "Awesome Image",
          category: "Web",
        },
        {
          imgName: "work-04.jpg",
          title: "Awesome Image",
          category: "Web",
        },
        {
          imgName: "work-05.jpg",
          title: "Awesome Image",
          category: "Print",
        },
        {
          imgName: "work-06.jpg",
          title: "Awesome Image",
          category: "Photography",
        },
        {
          imgName: "work-07.jpg",
          title: "Awesome Image",
          category: "Photography",
        },
        {
          imgName: "work-08.jpg",
          title: "Awesome Image",
          category: "Photography",
        },
      ],
      filtered: null,
    };
  },
  methods: {
    toggleActive: function (i) {
      this.shuffles.forEach((shuffle) => {
        shuffle.isActive = false;
      });
      this.shuffles[i].isActive = !this.shuffles[i].isActive;
      this.filtered = this.works.filter(
        (work) =>
          work.category == this.shuffles[i].text ||
          this.shuffles[i].text == "All"
      );
    },
  },
  computed: {
    worksSelected() {
      return this.filtered == null ? this.works : this.filtered;
    },
    // imagePath() {
    //   // eslint-disable-next-line no-undef
    //   return require(`@/assets/images/`);
    // },
  },
};
</script>
